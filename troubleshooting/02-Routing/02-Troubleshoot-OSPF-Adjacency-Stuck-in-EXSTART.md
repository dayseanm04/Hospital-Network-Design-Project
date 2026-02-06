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
- I used **show ip ospf neighbor** on the Edge Routers and Distribution Switches (See Below).

<img width="825" height="138" alt="EDGE-1" src="https://github.com/user-attachments/assets/cc88abe4-0b02-47de-a0df-fc5293f09d36" />

<img width="835" height="136" alt="EDGE-2" src="https://github.com/user-attachments/assets/ba528ad6-f707-421d-9c1f-729e7aafa00a" />

- Core firewalls not reaching **FULL** state
