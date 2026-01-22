# 🧪 Test – End-to-End Connectivity Between Hospital and INET Servers

## 📌 Overview

This test validates **bidirectional connectivity** between the **Hospital (HS) network** and **INET servers (The Internet)**.  

It confirms:
- **Layer 3 reachability** across the Internet
- **EtherChannel** from ISP1-R1 to the Hospital is working properly
- Successful **NAT translations**

## 🧠 Topology Context (Key Interfaces)

### Hospital ↔ ISP
- **HS-CORE-FW1 Port-Channel15 IP:** `69.45.12.2`
- **ISP1 Port-Channel15 IP:** `69.45.12.1`

## Reference Test Area

<img width="955" height="271" alt="topology" src="https://github.com/user-attachments/assets/551dcbda-fffc-477a-b147-ab2f41966938" />

---

## 🎯 Test Objectives
- Verify hospital → INET server reachability
- Verify INET server → hospital reachability
- Confirm INET NAT translations

---

## 🌐 INET Servers (Public IPs)

| Server | Function | Public IP |
|------|---------|-----------|
| INET-DNS-SRV | DNS | 200.10.0.2 |
| INET-WEB-SRV | Web | 200.10.0.4 |
| INET-NTP-SRV | NTP | 200.10.0.6 |

---

## ✅ Test 1 — Hospital to INET Server Reachability

### 🔍 Action
Ping each INET server public IP From **HS-CORE-FW1** :

<img width="848" height="406" alt="HS-CORE-FW1-Ping" src="https://github.com/user-attachments/assets/e003621c-316b-472a-a7d2-66809795dc48" />

✅ The pings test were successful



























