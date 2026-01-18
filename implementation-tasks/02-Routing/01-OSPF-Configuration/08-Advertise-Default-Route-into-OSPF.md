# 📡 Advertise Default Route into OSPF

## 📌 Overview
In this task, I will advertise the **default route (0.0.0.0/0)** into the hospital’s **internal OSPF routing domain** so internal router and switches know how to reach the internet.

The core firewall acts as the **OSPF Autonomous System Boundary Router (ASBR)** for the hospital network, and injects the default route into the hospital network/OSPF domain.

### ✅ Click ➡️ [here for the configure Default route on the HS-CORE-FW1 Task.](/implementation-tasks/02-Routing/Configure-Default-Routes-for-Internet-Access.md) 


## Reference Topology

<img width="968" height="310" alt="reference-topology" src="https://github.com/user-attachments/assets/87fc634c-6ce6-49ac-b1c1-fa64cdf7a90a" />

---

## 🎯 Objectives
- Advertise the internet default route into **OSPF**
