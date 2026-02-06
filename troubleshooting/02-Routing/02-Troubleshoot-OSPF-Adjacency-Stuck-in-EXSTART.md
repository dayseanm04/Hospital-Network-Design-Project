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

<img width="825" height="138" alt="EDGE-1" src="https://github.com/user-attachments/assets/cc88abe4-0b02-47de-a0df-fc5293f09d36" />

<img width="832" height="137" alt="Edge1-sucess" src="https://github.com/user-attachments/assets/28ed0a79-63c0-4f0e-8e07-759e0d97afea" />


- Core firewalls not reaching **FULL** state
- I used **show ip ospf neighbor** on the Edge Routers and Distribution Switches
