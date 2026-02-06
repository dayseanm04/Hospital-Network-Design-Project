# 🚨 Issue: OSPF Adjacency Stuck in EXSTART State

## 📌 Problem Description

After configuring **OSPF Area 0** across the hospital backbone, OSPF neighbor adjacencies involving the **core firewalls** failed to progress past the **EXSTART** state.

OSPF neighbors between Edge Routers and Distribution Switches formed successfully, but adjacencies to the Core Firewalls did not.

---

## 🌐 Affected Devices
- HS-EDGE-R1
- HS-EDGE-R2
- HS-CORE-FW1
- HS-CORE-FW2
- DSW1
- DSW2

---

## ❌ Symptoms Observed

- OSPF neighbors stuck in **EXSTART**
- Core firewalls not reaching **FULL** state
- I used **show ip ospf neighbor** on the Edge Routers and Distribution Switches
