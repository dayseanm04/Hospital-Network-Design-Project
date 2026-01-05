# 📡 Verify NTP Server IP Reachability

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













