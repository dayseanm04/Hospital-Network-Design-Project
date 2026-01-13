# 🧱 01 – Access Layer VLAN and SVI Preparation for HSRP

In this task, I **synchronize VLANs and configure SVIs** on the **Access Layer switches** to ensure both switches on each floor have **matching VLANs and correct gateway interfaces**.  
This step prepares the access layer for **HSRP** by standardizing VLAN and SVI IP addressing.

---

## 🎯 Objectives

- ✅ Ensure all required **VLANs exist** on each access switch
- ✅ Configure **SVIs** for each VLAN
- ✅ Apply a **consistent IP addressing standard**
- ✅ Prepare the access layer for **gateway redundancy (HSRP)**

---

## 🧠 SVI IP Addressing Standard

| Switch | SVI IP Assignment |
|------|-------------------|
| `F#-ASW1` | First usable IP address in the subnet |
| `F#-ASW2` | Second usable IP address in the subnet |

This approach keeps gateway addressing **clean, predictable, and easy to troubleshoot**.

---


## 🏥 Floor 1 — Emergency & Patient Services

| VLAN | Department | Subnet | F1-ASW1 SVI | F1-ASW2 SVI |
|----:|------------|--------|-------------|-------------|
| 101 | Emergency Department | 172.16.1.0/26 | 172.16.1.1 | 172.16.1.2 |
| 110 | X-Ray / Imaging | 172.16.1.64/26 | 172.16.1.65 | 172.16.1.66 |
| 120 | Nurse Station | 172.16.1.96/26 | 172.16.1.97 | 172.16.1.98 |


---


