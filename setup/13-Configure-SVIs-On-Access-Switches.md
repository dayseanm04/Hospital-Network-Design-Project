# 🧩 Configure SVIs on the Access Switches (Default Gateways)

**Goal:** Configure **SVIs** on each Access Switch so VLANs have a **default gateway** for routing.

## Refernce Netork Diagram

<img width="551" height="147" alt="reference-network-diagram" src="https://github.com/user-attachments/assets/530bc025-1921-4b91-89a4-ce4868f8dffb" />

---

## 📍 SVI IP Plan

### 🟦 F1-ASW1 SVIs
| VLAN | SVI IP (Gateway) | Subnet Mask |
|---:|---|---|
| 101 | 172.16.1.1 | 255.255.255.192 |
| 110 | 172.16.1.65 | 255.255.225.224 |
| 600 | 172.16.6.1 | 255.255.225.128 |

---

