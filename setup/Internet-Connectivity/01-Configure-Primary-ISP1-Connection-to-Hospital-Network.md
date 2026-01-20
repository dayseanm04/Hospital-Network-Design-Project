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

## Reference Topology

<img width="566" height="231" alt="new-topology" src="https://github.com/user-attachments/assets/34d66c7d-3033-4257-a20e-9ba8fad5be5b" />

---

## 🔌 Physical Connectivity Overview

| Device | Interface | Connected To | Interface |
|------|----------|-------------|-----------|
| ISP1 | G1/1/1 | HS-CORE-FW1 | G1/8 |
| ISP1 | G1/1/2 | HS-CORE-FW1 | G1/6 |
| ISP1 | G1/1/3 | INET-SW | G1/1/1 |
| ISP1 | G1/1/4 | INET-SW | G1/1/2 |

---

## ⚙️ Enable Layer 3 Routing on ISP1-R1

- Enable `ip routing`

---

## 🔗 Configure L3 EtherChannel (ISP1 ↔ Hospital Core Firewall)

### 📡 EtherChannel Details

| Parameter | Value |
|---------|------|
| Port-Channel | 15 |
| Subnet | 69.45.12.0 /30 |
| ISP1 Po15 IP | 69.45.12.1 |
| HS-CORE-FW1 Po15 IP | 69.45.12.2 |
| Mode | Static (on) |

## ISP1 Configuration (Port-channel15)

```bash
interface range g1/1/1-2
 no switchport
 no shutdown
 channel-group 15 mode on
```







