# 🧪 Test – End to End Connectivity Between Hospital and INET Servers

## Reference Test Area

<img width="955" height="271" alt="topology" src="https://github.com/user-attachments/assets/33782981-f1d4-47ca-a0f0-369fcc8c2dad" />

## 🧠 Topology 

### Hospital ↔ ISP
- **HS-CORE-FW1 Port-Channel15 IP:** `69.45.12.2`
- **ISP1 Port-Channel15 IP:** `69.45.12.1

---

## 📌 Overview

This test validates **bidirectional connectivity** between the **Hospital (HS) network** and **INET servers  (The internet)**. 

It confirms:
- **Layer 3 reachability** across the Internet edge
- **EtherChannel** from Hospital to the ISP1 is working properly
- Successful **NAT translations** on the ISP1 R1

---

## 🎯 Test Objectives

- Verify hospital → INET server reachability
- Verify INET server → hospital reachability
- Confirm NAT translations

---


## 🌐 INET Servers (Public IPs)

| Server | Function | Public IP |
|------|---------|-----------|
| INET-DNS-SRV | DNS | 200.10.0.2 |
| INET-WEB-SRV | Web | 200.10.0.4 |
| INET-NTP-SRV | NTP | 200.10.0.6 |

### 🔍 Action

Ping each INET server public IP from HS-CORE-FW1:


