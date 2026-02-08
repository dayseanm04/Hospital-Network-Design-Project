# 🌐 Configure OSPF Costs to Control Path Selection

## 📌 Overview
This this task, I will configure **OSPF interface costs** on **Port-Channels** to control **path selection**.

The goal is to ensure **predictable and symmetric routing** by influencing which distribution switch is preferred when multiple equal paths exist.

---

## 🎯 Objective
- Override the default OSPF cost on Port-Channels
- Prevent asymmetric routing and packet loss

---

## Reference Topology

<img width="753" height="464" alt="toplogy" src="https://github.com/user-attachments/assets/5e1d3339-2887-4283-8ee9-0771c4229a47" />

---

## 🧠 Design Logic

Each access switch is to both distribution 1 and 2 via **Port-Channels**.

Example (Floor 1):
- F1-ASW1 connects to:
  - **DSW1** via Port-Channel1
  - **DSW2** via Port-Channel2
- Default OSPF cost for all interfaces is **1**
- I will adjusted the OSPF cost is manually **control which path is preferred**


## 🔍 Default State (Before Change)

```bash
show ip ospf interface brief
```
<img width="927" height="154" alt="HS-EDGE-1" src="https://github.com/user-attachments/assets/1a5d7a99-cf03-4834-b4ad-7eb11a6f637e" />

<img width="963" height="240" alt="DSW1" src="https://github.com/user-attachments/assets/7a94a09c-799d-4a80-bdb2-37ece1722f17" />

<img width="929" height="169" alt="F1-ASW1" src="https://github.com/user-attachments/assets/c22e6ee5-b3c1-420b-9410-17110b2cf6bf" />



















