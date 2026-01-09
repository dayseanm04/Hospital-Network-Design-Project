# 🔗 Configure-HS-VOIP-R1-to-DSW1-P2P-Link

## 📌 Overview

In this Tassk I will configure a **Layer 3 point-to-point (P2P) link** between the **VoIP router (HS-VOIP-R1)** and **Distribution Switch 1 (DSW1)**.  

This link provides **connectivity** between the voice gateway and the distribution layer.

---

## 🧠 Link Details

| Item | Value |
|---|---|
| Network Type | Point-to-Point |
| Subnet | `10.200.0.0/30` |
| Router | HS-VOIP-R1 |
| Router Interface | `G0/0/0` |
| Switch | DSW1 |
| Switch Interface | `G1/1/4` |

## Reference Network Diagram

<img width="565" height="573" alt="network-diagram" src="https://github.com/user-attachments/assets/c419fe1f-ae0c-44e1-8873-5985956993e2" />

---


## ⚙️ Configuration Steps

### 1️⃣ Configure HS-VOIP-R1 G0/0/0 Interface

```bash
interface g0/0/0
ip address 10.200.0.1 255.255.255.252
no shutdown
```

### 2️⃣ Configure DSW1 Routed Interface

```bash
interface g1/1/4
no switchport
ip address 10.200.0.2 255.255.255.252
no shutdown
```

