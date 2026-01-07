# 📞 06-Voice-VLAN-Design.md

## 📌 Overview

This document describes the **Voice VLAN design** I will use in the network.  
Each department and floor has its **own dedicated Voice VLAN and subnet** to support **IP phones (VoIP)**.

Separating voice traffic from data traffic helps improve:

- 📈 Call quality
- 🔒 Security
- 🛠️ Network management

---

## Rerence Network Diagram

<img width="514" height="438" alt="reference-topology" src="https://github.com/user-attachments/assets/8297dd8b-a6ba-438a-8e18-a491de4070a0" />

---

## 🎯 Design Goals

- Assign **one Voice VLAN per floor or department**
- Use **clear VLAN numbering**
- Allocate **enough IP addresses** for IP phones
- Keep the design **simple and scalable**

---

## 🏥 Voice VLANs by Floor & Department

| Department / Location | Voice VLAN ID | Subnet | Subnet Size | Purpose |
|----------------------|---------------|--------|-------------|---------|
| Floor 1 – Voice | 160 | 172.16.10.0/25 | 126 hosts | IP phones on Floor 1 |
| Floor 2 – Voice | 260 | 172.16.20.0/25 | 126 hosts | IP phones on Floor 2 |
| Floor 3 – Voice | 360 | 172.16.30.0/25 | 126 hosts | IP phones on Floor 3 |
| Floor 4 – Voice | 460 | 172.16.40.0/25 | 126 hosts | IP phones on Floor 4 |
| IT Department – Voice | 60 | 172.16.60.0/27 | 30 hosts | IT department IP phones |

---

