# 🧪 06-test-IT-DPT-connectivity.md

## 🎯 Goal

Verify **basic connectivity** within the **IT Department (VLAN 240)** by testing:
- PC-to-PC communication
- PC-to-default-gateway communication

---

## 🌐 IT Department Network Info
| Item | Value |
|---|---|
| VLAN | **240 (IT-DPT)** |
| Subnet | **10.50.50.0/26** |
| Default Gateway (SVI) | **10.50.50.1** |
| IT-PC1 | **10.50.50.2** |
| IT-PC2 | **10.50.50.3** |

## 🧪 Test 1 

IT-PC1 ➜ IT-PC2
IT-PC1 ➜ IT-DPT Gateway

<img width="746" height="606" alt="PC1-pings" src="https://github.com/user-attachments/assets/54dd9c5e-1059-49e2-ad4c-aeb3dfb5d828" />


