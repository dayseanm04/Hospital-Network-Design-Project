# 🧭 Enable-OSPF-on-VoIP-Router-Loopback-and-P2P-Link

## 📌 Overview

In this task I will enable **OSPF routing** on the **VoIP Router** for:
- The **Loopback interface** (used by telephony-service)
- The **Point-to-Point (P2P) link** between the VoIP Router and **DSW1**

I will also enables OSPF on **DSW1** for the same P2P network to ensure full routing adjacency.

In all off the configurations I used **OSPF Process ID 1** and **Area 1**.

## Reference Network Diagram

<img width="796" height="371" alt="network-diagram" src="https://github.com/user-attachments/assets/4760b50a-76e8-452c-a214-d7eb81876b0f" />

---

## 🧠 OSPF Design Notes

- **Loopback interface** is advertised with a /32 wildcard
- **P2P link** uses a /30 network
- OSPF allows:
  - Reachability to the VoIP router
  - End-to-end routing for Voice VLANs
  - Integration with the rest of the hospital network

---

## 🔁 Enable OSPF on VoIP Router

### 1️⃣ Advertise Loopback Interface

```bash
router ospf 1
 network 10.0.0.13 0.0.0.0 area 1
```




















