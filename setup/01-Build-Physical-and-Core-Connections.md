# 🔌 Task 1 – Build Physical and Core Connections
I will be building the **physical and logical connections** between the ISP, hospital core devices, distribution switches, and access switches.

I havent configured IP addressing or routing in this task.  
The goal is to ensure all devices are **properly connected and ready for configuration**.

## 🛜 1. ISP1 Router Information
- Device Type: Cisco PT-Router
- Hostname: ISP1-R1
- Interfaces:
  - G0/0 – G0/3 → Fiber
  - G0/4 – G0/5 → Serial
  - G0/6 – G0/9 → Gigabit Ethernet
 
---

## 🔐 2. Hospital Core Firewall Information
- Device: Cisco ASA 5506
- Hostname: HS-Core-FW
- Interfaces:
  - G1/1 – G1/8 → Gigabit Ethernet

---

## 🧠 3. Hospital Core Router Information
- Device: Cisco PT-Router
- Hostname: HS-Core-R1
- Interfaces:
  - G0/0 – G0/1 → Gigabit Ethernet
  - G0/2 – G0/9 → Fiber

## 🔗 4. ISP to Hospital Core Firewall Connections
Connect the ISP router to the hospital firewall for security and redundancy.

| ISP Router Interface | Firewall Interface |
|----------------------|--------------------|
| ISP1-R1 G9/0 | HS-Core-FW G1/8 |

---

## 🔗 5. Firewall to Hospital Core Router Connections

Connect the firewall to the hospital core router.

| Firewall Interface | Core Router Interface |
|--------------------|-----------------------|
| HS-Core-FW G1/7 | HS-CORE-R1 G0/0 |

## 🏛️ 6. Distribution Switch Connections

### Distribution Switch Information
- Model: Cisco 3650-24PT
- Devices: DSW1 and DSW2

---

### DSW1 to Core Router
| DSW1 Interface | Core Router Interface | Media |
|---------------|----------------------|-------|
| G1/1/1 | HS-CORE-R1 G2/0 | Fiber |

### DSW2 to Core Router
| DSW2 Interface | Core Router Interface | Media |
|---------------|----------------------|-------|
| G1/1/1 | HS-CORE-R1 G3/0 | Fiber |

✔️ These connections will support redundancy and load balancing.

---

## 🔄 7. Distribution Switch Interconnection

Connect the two distribution switches together.

| DSW1 Interface | DSW2 Interface | Media |
|---------------|---------------|-------|
| G1/1/2 | G1/1/2 | Fiber |
| G1/1/3 | G1/1/3 | Fiber |

✔️ These links will later be bundled using EtherChannel.

---

## 🏢 8. Access Switch Connections

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

## ✅ 9. Task Completion Checklist

- ✅ ISP router connected to hospital firewall  
- ✅ Firewall connected to the hospital core router  
- ✅ Core router is connected to the distribution switches  
- ✅ Distribution switches are interconnected  
- ✅ Access switches has dual connections to the distribution layers


## 📌 Note:
Note that I may update the connections when nessasry

## Network Diagram:

<img width="641" height="443" alt="03-diagram" src="https://github.com/user-attachments/assets/4fde28c9-d99e-4c8c-9422-248902706a6e" />


