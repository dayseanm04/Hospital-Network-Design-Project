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

## 🔍 Troubleshooting Steps Taken
- 1️⃣ Verified physical interfaces and Port-Channels were up/up
- 2️⃣ Confirmed correct IP addressing on all OSPF links
- 3️⃣ I Ran **`show running-config | section Port`** on on HS-CORE-FW1 and HS-CORE-FW2. (See Below)

<img width="720" height="223" alt="CORE-FW1" src="https://github.com/user-attachments/assets/4794b5a2-d95a-425b-bf2d-e109006b029b" />

<img width="810" height="211" alt="CORE-FW2" src="https://github.com/user-attachments/assets/4f7db3cb-abc1-4120-9d48-f5e31c80f8a4" />












