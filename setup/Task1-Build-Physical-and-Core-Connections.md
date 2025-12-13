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


