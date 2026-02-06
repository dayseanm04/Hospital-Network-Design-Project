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

<img width="837" height="243" alt="DSW1" src="https://github.com/user-attachments/assets/0386d9e8-5b9f-423d-9cba-998ce12c8b2f" />

<img width="849" height="261" alt="DSW2" src="https://github.com/user-attachments/assets/1b647b04-5f4e-494f-80d9-04bf61902caf" />


- The Core firewalls did not reach **FULL** state

## 🔍 Troubleshooting Steps Taken
- 1️⃣ Verified physical interfaces and Port-Channels were up/up
- 2️⃣ Confirmed correct IP addressing on all OSPF links
- 3️⃣ I Ran **`show running-config | section Port`** on on HS-CORE-FW1 and HS-CORE-FW2. (See Below)

<img width="720" height="223" alt="CORE-FW1" src="https://github.com/user-attachments/assets/4794b5a2-d95a-425b-bf2d-e109006b029b" />

<img width="810" height="211" alt="CORE-FW2" src="https://github.com/user-attachments/assets/4f7db3cb-abc1-4120-9d48-f5e31c80f8a4" />

- I am missing nameif  and security level configuration on firewall Port-Channels

---

## 🛠 Root Cause

The Port-Channel interfaces on the core firewalls did not have nameif configured.

On Cisco firewalls, interfaces without a nameif are not fully operational for routing protocols, which prevented OSPF from completing adjacency formation.

---

## ✅ Resolution

Configured **nameif** and security levels on all firewall Port-Channels connected to:

- Edge Routers
- Distribution Switches

## ♦️ Config summary:

In Global Config mode On HS-CORE-FW1:

- interface Port-channel1
- nameif OUTSIDE-ISP1
- security-level 0
- interface Port-channel20
- nameif INSIDE-A
- security-level 100

In Global Config mode On HS-CORE-FW2:

- interface Port-channel1
- nameif OUTSIDE-ISP2
- security-level 0
- interface Port-channel20
- nameif INSIDE-B
- security-level 100

## 🧪 Verification

### show ip ospf neighbor on HS-EDGE-R1

<img width="832" height="137" alt="Edge1-sucess" src="https://github.com/user-attachments/assets/e6f0369e-8484-4fde-a45c-dab378e81fec" />

### show ip ospf neighbor on HS-EDGE-R2

<img width="840" height="135" alt="Edge2-sucess" src="https://github.com/user-attachments/assets/b768e125-41a3-4b91-83c8-2fb183cd27cc" />
















