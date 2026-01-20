# 🌐 01 – Configure Primary ISP1 Connection to Hospital Network

## 📌 Overview

In this task, I will configure the **primary Internet connection between ISP1 and the hospital network**.  

Due to **Cisco Packet Tracer limitations**, EtherChannel cannot be configured on router platforms.  
To support **Layer 3 EtherChannel**, I used a **Layer 3 switch**.

---

## 🎯 Objectives

- Establish new physical links between ISP1 and the hospital
- Enable Layer 3 routing on the ISP edge device
- Configure **Layer 3 EtherChannel** for:
  - ISP1 ↔ Hospital core firewall
- Assign IP addresses

---

## 🔌 Physical Connectivity Overview

| Device | Interface | Connected To | Interface |
|------|----------|-------------|-----------|
| ISP1 | G1/1/1 | HS-CORE-FW1 | G1/8 |
| ISP1 | G1/1/2 | HS-CORE-FW1 | G1/6 |
| ISP1 | G1/1/3 | INET-SW | G1/1/1 |
| ISP1 | G1/1/4 | INET-SW | G1/1/2 |

---

## ⚙️ Enable Layer 3 Routing on ISP Device

- Enable `ip routing`

---
