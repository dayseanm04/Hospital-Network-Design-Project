# 🌐 Configure ISP1 to HS-EDGE-R1 and R2 L3 Port-Channels

## 📌 Overview

In this task, I will configure **Layer 3 static Port-Channels** between **ISP1-R1** and the hospital **edge routers (HS-EDGE-R1 and HS-EDGE-R2)**.

Each edge router has a redundant uplink to ISP1 using an L3 EtherChannel.

## 🎯 Objectives

- Configure **Layer 3 EtherChannel** for:
  - ISP1 ↔ Hospital edge routers
- Assign IP addresses

## Reference Topology

<img width="391" height="299" alt="topology" src="https://github.com/user-attachments/assets/62090ef2-aa08-4f17-b0bf-7b54a2e56c3c" />

---

# 🧱 ISP1 ↔ HS-EDGE-R1 Interconnection

## 🔌 Physical Connections

| Device | Interface | Connected To | Interface |
|--------|-----------|--------------|-----------|
| HS-EDGE-R1 | G1/1/1 | ISP1-R1 | G1/1/1 |
| HS-EDGE-R1 | G1/1/2 | ISP1-R1 | G1/1/2 |

---

## 🔧 ISP1-R1 Configuration (Po15)

```bash
interface range g1/1/1-2
 no switchport
 no shutdown
 channel-group 15 mode on

interface port-channel15
 ip address 69.45.12.1 255.255.255.252
```







