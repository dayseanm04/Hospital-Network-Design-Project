# 📞 Configure VoIP Router HS R2

## 📌 Overview

This task covers the **initial setup of the VoIP router (HS-R2)** used in the Hospital Network Design project.  

The router acts as the **voice gateway** and supports **Cisco telephony-service**, which is required for IP phones in Packet Tracer.

**⚠️ Note:**  
Although the hospital network is designed for many VoIP phones, only a limited number are deployed in the topology due to **Packet Tracer limitations**.

## Reference Network Diagram

<img width="634" height="578" alt="network-diagram" src="https://github.com/user-attachments/assets/d821f31d-a29a-4ffb-b593-67ff3e9acbaa" />

---

## 🧠 Key Information
- **Router Model:** Cisco 2811  
- **Router Hostname:** HS-R2  
- **Purpose:** Voice gateway for IP phones  
- **Max IP Phones Supported:** 42 (Packet Tracer limit)  
- **Connected To:** Distribution Switch (DSW1)

---

## 🔗 Network Connectivity
| Item | Details |
|----|--------|
| Router Interface | `G0/0/0` |
| Connected Switch | `DSW1` |
| Switch Interface | `G1/1/4` |
| Link Type | Fiber |
| Network Type | Point-to-Point |
| P2P Subnet | `10.200.0.0/30` |

---

## ⚙️ Basic Router Configuration

### 1️⃣ Enter Global Configuration Mode

```bash
enable
configure terminal
```

### 2️⃣ Set the Hostname

```bash
hostname VOIP-Router
```

### 3️⃣ Configure the Uplink Interface to DSW1

```bash
interface g0/0/0
description To-DSW1-G1/1/4
```
