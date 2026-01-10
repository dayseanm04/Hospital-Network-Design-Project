# 🔊 Configure-Voice-VLAN-SVIs-on-Access-Switches

## 📌 Overview

I this task I will configure **SVIs (Switched Virtual Interfaces)** for the **Voice VLANs** on the **Access Switches**.  
Each SVI provides the **default gateway** for IP phones in that Voice VLAN.

## Reference Network Diagram

<img width="796" height="371" alt="network-diagram" src="https://github.com/user-attachments/assets/4760b50a-76e8-452c-a214-d7eb81876b0f" />

---

## 🧠 Voice SVI Plan (Gateways)
| Access Switch | Voice VLAN | SVI / Default Gateway | Subnet Mask |
|---|---:|---|---|
| F1-ASW1 | 160 | 172.16.10.1 | 255.255.255.128 |
| F2-ASW1 | 260 | 172.16.20.1 | 255.255.255.128 |
| F3-ASW1 | 360 | 172.16.30.1 | 255.255.255.128 |
| Service-ASW | 60 | 172.16.60.1 | 255.255.255.224 |

---

