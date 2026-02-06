# 🌐 Expand Network Design with Secondary ISP and Redundant Edge Part 1

In this task, I will expand the **hospital network design**. I will add a secondary Router and Firewall. This improves availability and removes single points of failure at the network edge.

---

## 🎯 Objectives
- ✅ Add a **secondary ISP** for redundancy
- ✅ Add an **edge router**
- ✅ Implement **redundant Layer 3 links** using port channels

## Reference Topology

<img width="1281" height="535" alt="Screenshot 2026-02-04 160733" src="https://github.com/user-attachments/assets/b293ed65-e9e3-475e-abb3-16119b7765ab" />

---

## 🧠 Design Change Overview

**Before**
- Single ISP
- Single edge path (HS-CORE-R1 i renamed it HS-EDGE-R1)

**After**
- Dual ISP connectivity
- Redundant edge routers and firewall paths

## 🌍 ISP Overview

| ISP | Purpose |
|---|---|
| ISP1 | Primary Internet provider |
| ISP2 | Secondary Internet provider (redundancy / failover) |


## 🔗 New Devices

| Device | Role |
|---|---|
| ISP2-R1 | Secondary ISP router |
| HS-EDGE-R2 | Secondary Hospital Edge Router |
| HS-CORE-R2 | Secondary Core Firewall |


## 🔀 Layer 3 Port Channel Summary

### ♦️ ISP to Hospital Edge Routers

| Port Channel | Connected Devices | Purpose | Network |
|---|---|---|---|
| Po15 | HS-EDGE-R1 ↔ ISP1-R1 | Primary ISP routed uplink | 69.45.12.0/30 |
| Po15 | HS-EDGE-R2 ↔ ISP2-R1 | Secondary ISP routed uplink | 100.45.12.0/30 |

### ♦️ ISP1-R1 to ISP2-R1

| Port Channel | Connected Devices | Network |
|---|---|---|
| Po10 | ISP1-R1 ↔ ISP2-R1 | 10.50.50.0/30 |


### ♦️ Hospital Edge Router to Hospital Core Firewalls

| Port Channel | Connected Devices | Network |
|---|---|---|
| Po1 | HS-EDGE-R1 ↔ HS-CORE-FW1 | 10.200.0.0/30 |
| Po1 | HS-EDGE-R2 ↔ HS-CORE-FW2 | 10.200.0.4/30 |


### ♦️ Hospital Core Firewall to Hospital Core Firewall

| Port Channel | Connected Devices | Network |
|---|---|---|
| Po10 | HS-CORE-FW1 ↔ HS-CORE-FW2 | 10.150.0.0/30 |




