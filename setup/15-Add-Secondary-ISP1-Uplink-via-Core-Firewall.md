# 🌐 15 Add Secondary ISP1 Uplink via Core Firewall

## 📌 Overview

In this task I will add a **secondary uplink to ISP1** through the **core firewall** to eliminate a single point of failure in the hospital’s network.

Previously, the hospital relied on **one ISP1 connection**, meaning a link failure would result in an outage.  

## Reference Topology

<img width="566" height="231" alt="new-topology" src="https://github.com/user-attachments/assets/34d66c7d-3033-4257-a20e-9ba8fad5be5b" />

---

## 🎯 Objectives

- Add a new **ISP1-to-Core Firewall** point-to-point link  
- Assign **static IP addresses** on all involved interfaces  
- Configure firewall **interface roles and security levels**  

---

## 🔌 New Physical Connections

### ISP1 to Core Firewall
| Device | Interface |
|------|----------|
| ISP1-R1 | G1/1/2 |
| HS-CORE-FW1 | G1/6 |

---

### Core Firewall to Core Router
| Device | Interface | IP Address | Subnet |
|------|----------|-----------|--------|
| HS-CORE-FW1 | G1/5 | 10.255.255.5 | /30 |
| HS-CORE-R1 | G1/0 | 10.255.255.6 | /30 |
| **Network** | — | **10.255.255.4** | /30 |
