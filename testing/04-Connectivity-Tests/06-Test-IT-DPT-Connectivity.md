# 🧪 06-test-IT-DPT-connectivity.md

## 🎯 Goal

Verify **basic connectivity** within the **IT Department (VLAN 240)** by testing:
- PC-to-PC communication
- PC-to-default-gateway communication

## Reference Network Diagram

<img width="446" height="178" alt="reference-network-diagram" src="https://github.com/user-attachments/assets/716ba13b-0a9e-4e43-bb3f-954d5cc47f48" />


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

#### ♦️ IT-PC1 pings IT-DPT Gateway (10.50.50.1)

#### ♦️ IT-PC1 pings IT-PC2 (10.50.50.3)

<img width="746" height="606" alt="IT-PC1-pings" src="https://github.com/user-attachments/assets/54dd9c5e-1059-49e2-ad4c-aeb3dfb5d828" />

## 🧪 Test 2

#### ♦️ IT-PC2 pings IT-DPT Gateway (10.50.50.1)

#### ♦️ IT-PC2 pings IT-PC1 (10.50.50.2)

<img width="742" height="612" alt="IT-PC2-pings" src="https://github.com/user-attachments/assets/c5991922-5829-4649-aff3-56904c280d73" />

## 🧪 Test 2

#### ♦️ Service-ASW pings IT-PC1 (10.50.50.2)

#### ♦️ Service-ASW pings IT-PC2 (10.50.50.3)

<img width="723" height="262" alt="Service-ASW-pings" src="https://github.com/user-attachments/assets/793968a5-94ec-47b6-b564-67dc487aa04e" />

