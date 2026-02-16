# 🔌 Task 1 – Build Physical and Core Connections
I will be building the **physical and logical connections** between the ISP, hospital core devices, distribution switches, and access switches.

I havent configured IP addressing or routing in this task.  
The goal is to ensure all devices are **properly connected and ready for configuration**.

## 🛜 1. ISP1 Router Information
- Device Type: Cisco 3650-24PS
- Hostname: ISP1-R1
 
---

## 🔐 2. Hospital Core Firewalls Information
- Device: Cisco ASA 5506
- Hostname: HS-Core-FW1
- Hostname: HS-Core-FW2
- Interfaces:
  - G1/1 – G1/8 → Gigabit Ethernet

---

## 🧠 3. Hospital Edge Router Information
- Device: Cisco 3650-24PS
- Hostname: HS-EDGE-R1
- Hostname: HS-EDGE-R2

## 🔗 4. ISP1 to Hospital Edge Routers Connections
Connect the ISP router to the hospital edge routers.

| ISP Router Interface | Edge Router Interface | Port Channel |
|----------------------|--------------------|-------|
| ISP1-R1 G1/1/1 | HS-EDGE-R1 G1/1/1 | 15 |
| ISP1-R1 G1/1/2 | HS-EDGE-R1 G1/1/2 | 15 |
| ISP2-R1 G1/1/3 | HS-EDGE-R2 G1/1/1 | 10 |
| ISP2-R2 G1/1/4 | HS-EDGE-R2 G1/1/2 | 10 |

---

## 🔗 5. Edge Routers interonnections

| HS-EDGE-R1 interface | HS-EDGE-R2 interface | Port Channel |
|--------------------|-----------------------|-------|
| HS-EDGE-R1 G1/0/23 | HS-EDGE-R2 G1/0/23 | 10 |
| HS-EDGE-R1 G1/0/24 | HS-EDGE-R2 G1/0/24 | 10 |

---

## 🔗 6. Firewall to Hospital Edge Router Connections

Connect the core firewalls to the hospital edge routers.

| Firewall Interface | Edge Router Interface | Port Channel |
|--------------------|-----------------------|-------|
| HS-CORE-FW1 G1/1 | HS-EDGE-R1 G1/1/3 | 1 |
| HS-CORE-FW1 G1/2 | HS-EDGE-R1 G1/1/4 | 1 |
| HS-CORE-FW2 G1/1 | HS-EDGE-R2 G1/1/3 | 1 |
| HS-CORE-FW2 G1/2 | HS-EDGE-R2 G1/1/4 | 1 |

## 🏛️ 8. Distribution Switch Connections

### Distribution Switch Information
- Model: Cisco 3650-24PT
- Devices: DSW1 and DSW2

---

### DSW1 to Core Firewall

| DSW1 Interfaces | Core Firewall Interfaces | Port Channel |
|---------------|----------------------|-------|
| G1/1/1 | HS-CORE-FW1 G1/3 | 20 |
| G1/1/4 | HS-CORE-FW1 G1/4 | 20 |

| DSW1 Interfaces | Core Router Interfaces | Port Channel |
|---------------|----------------------|-------|
| G1/1/1 | HS-CORE-FW2 G1/3 | 20 |
| G1/1/4 | HS-CORE-FW2 G1/4 | 20 |

---

## 🔄 8. Distribution Switch Interconnection

Connect the two distribution switches together.

| DSW1 Interface | DSW2 Interface | Port Channel |
|---------------|---------------|-------|
| G1/1/2 | G1/1/2 | 10 |
| G1/1/3 | G1/1/3 | 10 |

✔️ These links will later be bundled using EtherChannel.

---

## 🏢 9. Access Switch Connections

### Access Switch Information
- Model: Cisco 3650-24PT
- Devices: F1-ASW1, F1-ASW2 F2-ASW1, F2-ASW2, F3-ASW1, F3-ASW2 and Service-ASW

---

### F1-ASW1 Connections
| F1-ASW1 Interface | Distribution Switch | Interface |
|---------------|---------------------|-----------|
| G1/0/24 | DSW1 | G1/0/1 |
| G1/0/23 | DSW1 | G1/0/2 |
| G1/0/22 | DSW2 | G1/0/1 |
| G1/0/21 | DSW2 | G1/0/2 |

---

### F1-ASW2 Connections
| F1-ASW1 Interface | Distribution Switch | Interface |
|---------------|---------------------|-----------|
| G1/0/24 | DSW1 | G1/0/3 |
| G1/0/23 | DSW1 | G1/0/4 |
| G1/0/22 | DSW2 | G1/0/3 |
| G1/0/21 | DSW2 | G1/0/4 |

---

### F2-ASW1 Connections
| F2-ASW1 Interface | Distribution Switch | Interface |
|---------------|---------------------|-----------|
| G1/0/24 | DSW1 | G1/0/5 |
| G1/0/23 | DSW1 | G1/0/6 |
| G1/0/22 | DSW2 | G1/0/5 |
| G1/0/21 | DSW2 | G1/0/6 |

---

### F2-ASW2 Connections
| F2-ASW2 Interface | Distribution Switch | Interface |
|---------------|---------------------|-----------|
| G1/0/24 | DSW1 | G1/0/7 |
| G1/0/23 | DSW1 | G1/0/8 |
| G1/0/22 | DSW2 | G1/0/7 |
| G1/0/21 | DSW2 | G1/0/8 |

---

### F3-ASW1 Connections
| F3-ASW1 Interface | Distribution Switch | Interface |
|---------------|---------------------|-----------|
| G1/0/24 | DSW1 | G1/0/9 |
| G1/0/23 | DSW1 | G1/0/10 |
| G1/0/22 | DSW2 | G1/0/9 |
| G1/0/21 | DSW2 | G1/0/10 |

---

### F3-ASW2 Connections
| F3-ASW2 Interface | Distribution Switch | Interface |
|---------------|---------------------|-----------|
| G1/0/24 | DSW1 | G1/0/11 |
| G1/0/23 | DSW1 | G1/0/12 |
| G1/0/22 | DSW2 | G1/0/11 |
| G1/0/21 | DSW2 | G1/0/12 |

---

### Service-ASW Connections
| Service-ASW Interface | Distribution Switch | Interface |
|---------------|---------------------|-----------|
| G1/0/24 | DSW1 | G1/0/13 |
| G1/0/23 | DSW1 | G1/0/14 |
| G1/0/22 | DSW2 | G1/0/13 |
| G1/0/21 | DSW2 | G1/0/14 |

✔️ Each access switch has **dual uplinks** for redundancy.

---

## ✅ Task Completion Checklist

- ✅ ISP router connected to hospital Edge Routers  
- ✅ Edge Routers connected to the hospital core firewalls  
- ✅ Hospital core firewalls  is connected to the distribution switches
- ✅ Hospital Edge Routers are interconnected  
- ✅ Distribution switches are interconnected  
- ✅ Access switches has dual connections to the distribution switches

## 📌 Note:
Note that I may update the connections when nessasry

## Network Diagram:

<img width="703" height="519" alt="topology" src="https://github.com/user-attachments/assets/1ecc7cd6-13c3-4faf-95a8-56ae3692cfc8" />
