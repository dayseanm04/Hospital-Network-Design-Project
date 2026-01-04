# Setup IT Department Network 

## 🎯 Goal

Set up the **IT Department** on the **Service-ASW** by creating **VLAN 240**, assigning ports for IT PCs, configuring the 
**SVI (default gateway)**, and configuring **static IPs** on the IT PCs.

## Refernce Network Diagram

<img width="446" height="178" alt="reference-network-diagram" src="https://github.com/user-attachments/assets/12fda8fc-4dde-4434-848d-2d194839adfe" />

---

## 🌐 IT Department Network Info
| Item | Value |
|---|---|
| VLAN | **240**  |
| VLAN Name | **IT-DPT** |
| Subnet | **10.50.50.0/26** |
| SVI / Default Gateway | **10.50.50.1/26**  |
| Subnet Mask | **255.255.255.192** |

---

## 🔌 PC Connections
| Device | Switch | Port |
|---|---|---|
| IT-PC1 | Service-ASW | **G1/0/9** |
| IT-PC2 | Service-ASW | **G1/0/10** |

---
