# 🧪 Test HS-CORE-R1 to HS-CORE-FW1 Connectivity

## 📌 Purpose
The purpose of this test is to verify **Layer 3 connectivity** between the **HS-CORE-R1 router** and the **HS-CORE-FW1 firewall** over their point-to-point link.  


## Refernce Diagram

<img width="569" height="263" alt="HS1-CORE-FW1-HS-CORE-R1" src="https://github.com/user-attachments/assets/8955fd02-a101-4e98-97c5-6484cc844c8f" />

---

## 🌐 Network Information

| Device | Interface Role | IP Address | Subnet |
|------|---------------|-----------|--------|
| HS-CORE-R1 | Core Router | 10.255.255.2 | /30 |
| HS-CORE-FW1 | Firewall | 10.255.255.1 | /30 |
| Network | P2P Link | 10.255.255.0 | /30 |

---


## 🧪 Connectivity Tests (Ping)

### 📌 Ping Test Plan

| Test # | Source | Destination |
|------:|--------|-------------|
| 1 | HS-CORE-R1 | 10.255.255.1 (HS-CORE-FW1) |
| 2 | HS-CORE-FW1 | 10.255.255.2 (HS-CORE-R1) |


## 📝 Ping Results 

#### Test 1: HS-CORE-R1 to 10.255.255.1 
