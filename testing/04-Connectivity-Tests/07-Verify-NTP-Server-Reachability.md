# 📡 Verify NTP Server Reachability

## 📌 Overview

This test verifies **Layer 3 network connectivity** between the **NTP server** and the rest of the hospital network.

The purpose of this test is to ensure that the NTP server is **reachable from key network devices** before configuring time synchronization on routers and switches.

---

## 🎯 Test Objective

Confirm that:
- The NTP server can reach its default gateway
- The default gateway can reach the NTP server
- Distribution switches can reach the NTP server

---

## 🏥 NTP Server Information

| Item | Value |
|----|----|
| Device | NTP-SRV |
| IP Address | 10.10.10.3 |
| Default Gateway | 10.10.10.1 |
| VLAN | Servers VLAN |

---

## 🧪 Connectivity Tests Performed

### 🔹 Test 1: NTP Server → Default Gateway


<img width="744" height="376" alt="NTP-SRV-ping" src="https://github.com/user-attachments/assets/93b243d4-97ad-4857-8328-beb1f52812f2" />

### 🔹 Test 2: Service-ASW → NTP SRV

<img width="697" height="154" alt="Service-ASW1-ping-NTP-SRV" src="https://github.com/user-attachments/assets/53800c7c-ee7e-470a-b9d6-12f1d0754a6d" />

### 🔹 Test 3: DSW1 → NTP SRV

<img width="826" height="155" alt="DSW1-ping-NTP-SRV" src="https://github.com/user-attachments/assets/8a2fd3bc-fab5-4a67-ba6a-3227bc87894c" />


### 🔹 Test 4: DSW2 → NTP SRV

<img width="765" height="156" alt="DSW2-ping-NTP-SRV" src="https://github.com/user-attachments/assets/ed708aff-e490-42fc-b5b5-c99e86da40ae" />







