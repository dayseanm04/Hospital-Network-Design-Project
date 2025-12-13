# 🔌 Task 1 – Build Physical and Core Connections

This task focuses on building the **physical and logical connections** between the ISP, hospital core devices, distribution switches, and access switches.

I havent configured IP addressing or routing in this task.  
The goal is to ensure all devices are **properly connected and ready for configuration**.

## 🛜 1. ISP1 Router Information
- Device Type: Cisco PT-Router
- Hostname: ISP1-R1
- Interfaces:
  - G0/0–G0/4 → Fiber
  - G0/5–G0/9 → Gigabit Ethernet
 
---

## 🔐 2. Hospital Core Firewall Information
- Device: Cisco ASA 5506
- Hostname: HS-Core-FW
- Interfaces:
  - G1/1–G1/9 → Gigabit Ethernet

---

## 🧠 3. Hospital Core Router Setup Information
- Device: Cisco PT-Router
- Hostname: HS-Core-R1
- Interfaces:
  - G0/0–G0/1 → Gigabit Ethernet
  - G0/2–G0/9 → Fiber

## 🔗 4. ISP to Hospital Core Firewall Connections
Connect the ISP router to the hospital firewall for security and redundancy.

| ISP Router Interface | Firewall Interface |
|----------------------|--------------------|
| ISP1-R1 G5/0 | HS-Core-FW G1/1 |
| ISP1-R1 G6/0 | HS-Core-FW G1/2 |

---

## 🔗 5. Firewall to Hospital Core Router Connections

Connect the firewall to the hospital core router.

| Firewall Interface | Core Router Interface |
|--------------------|-----------------------|
| HS-Core-FW G1/3 | HS-CW-R1 G0/0 |
| HS-Core-FW G1/4 | HS-CW-R1 G1/0 |

## 🏛️ 6. Distribution Switch Connections

### **Distribution Switch Information**
- Model: Cisco 3650-24PT
- Devices: DSW1 and DSW2

---

### DSW1 to Core Router
| DSW1 Interface | Core Router Interface | Media |
|---------------|----------------------|-------|
| G1/1/1 | HS-CW-R1 G2/0 | Fiber |
| G1/1/2 | HS-CW-R1 G3/0 | Fiber |

### DSW2 to Core Router
| DSW2 Interface | Core Router Interface | Media |
|---------------|----------------------|-------|
| G1/1/1 | HS-CW-R1 G4/0 | Fiber |
| G1/1/2 | HS-CW-R1 G5/0 | Fiber |

✔️ These connections will support redundancy and load balancing.

---

## 🔄 7. Distribution Switch Interconnection

Connect the two distribution switches together.

| DSW1 Interface | DSW2 Interface | Media |
|---------------|---------------|-------|
| G1/1/3 | G1/1/3 | Fiber |
| G1/1/4 | G1/1/4 | Fiber |

✔️ These links will later be bundled using EtherChannel.

---

## 🏢 8. Access Switch Connections

### **Access Switch Information**
- Model: Cisco 3650-24PT
- Devices: ASW1, ASW2, ASW3

---

### Floor1-ASW1 Connections
| Floor1-ASW1 Interface | Distribution Switch | Interface |
|---------------|---------------------|-----------|
| G1/0/24 | DSW1 | G1/0/1 |
| G1/0/23 | DSW1 | G1/0/2 |
| G1/0/22 | DSW2 | G1/0/1 |
| G1/0/21 | DSW2 | G1/0/2 |

---

### **Floor2-ASW1 Connections**
| Floor2-ASW1 Interface | Distribution Switch | Interface |
|---------------|---------------------|-----------|
| G1/0/24 | DSW1 | G1/0/3 |
| G1/0/23 | DSW1 | G1/0/4 |
| G1/0/22 | DSW2 | G1/0/3 |
| G1/0/21 | DSW2 | G1/0/4 |

---

### **Floor3-ASW1 Connections**
| Floor3-ASW1 Interface | Distribution Switch | Interface |
|---------------|---------------------|-----------|
| G1/0/24 | DSW1 | G1/0/5 |
| G1/0/23 | DSW1 | G1/0/6 |
| G1/0/22 | DSW2 | G1/0/5 |
| G1/0/21 | DSW2 | G1/0/6 |

✔️ Each access switch has **dual uplinks** for redundancy.

---

## ✅ 9. Task Completion Checklist

- ✅ ISP router connected to hospital firewall  
- ✅ Firewall connected to the hospital core router  
- ✅ Core router is connected to the distribution switches  
- ✅ Distribution switches are interconnected  
- ✅ Access switches hab dual connections to the distribution layers


## 📌 Note:
Note that I may update the connections when nessasry

