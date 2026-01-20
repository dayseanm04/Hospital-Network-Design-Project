# 🌐 15 Add Secondary ISP1 Uplink via Core Firewall

## 📌 Overview

In this task I will add a **secondary uplink to ISP1** through the **core firewall** to eliminate a single point of failure in the hospital’s network.

Previously, the hospital relied on **one ISP1 connection**, meaning a link failure would result in an outage.  

## Reference Topology

<img width="968" height="310" alt="reference-topology" src="https://github.com/user-attachments/assets/87fc634c-6ce6-49ac-b1c1-fa64cdf7a90a" />

---

## 🎯 Objectives

- Add a new **ISP1-to-Core Firewall** point-to-point link  
- Assign **static IP addresses** on all involved interfaces  
- Configure firewall **interface roles and security levels**  

---

## 🔌 New Physical Connections

### ISP1 to Core Firewall
| Device | Interface | IP Address | Subnet |
|------|----------|-----------|--------|
| ISP1-R1 | G8/0 | 69.45.12.5 | /30 |
| HS-CORE-FW1 | G1/6 | 69.45.12.6 | /30 |
| **Network** | — | **69.45.12.4** | /30 |

---

### Core Firewall to Core Router
| Device | Interface | IP Address | Subnet |
|------|----------|-----------|--------|
| HS-CORE-FW1 | G1/5 | 10.255.255.5 | /30 |
| HS-CORE-R1 | G1/0 | 10.255.255.6 | /30 |
| **Network** | — | **10.255.255.4** | /30 |

---
