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

<img width="752" height="131" alt="HS-CORE-R1-To-HS-CORE-FW1-failed" src="https://github.com/user-attachments/assets/b397a990-92a5-4ef5-a872-b7da046947d4" />

#### Test 2: HS-CORE-FW1 to 10.255.255.2

<img width="749" height="126" alt="HS-CORE-FW1-To-HS-CORE-R1-failed" src="https://github.com/user-attachments/assets/b058801b-6f75-4e82-a5a9-7df067fede99" />
 
The ping test Failed so I have to troubleshoot.

---

## 🛠 Troubleshooting: [HS-CORE-R1 → HS-CORE-FW1 Ping Failure](../troubleshooting/01-Connectivity-Issues/Issue-HS-CORE-R1-To-HS-CORE-FW1-Ping-Failure.md)
