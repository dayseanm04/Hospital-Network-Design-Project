# 🌐 Configure IP addresses for HS-CORE-FW1 ↔ HS-CORE-R1

This document covers the point-to-point Layer 3 connection between the **Hospital Core Firewall (HS-CORE-FW1)** and 
the **Hospital Core Router (HS-CORE-R1)**.

✅ I used a **private IP subnet** for this link because it is an internal connection.  
📌 **Note:** Dynamic routing is **not configured yet** in this phase.

---

## 🔗 Physical Connection

| Device | Interface | Connected To | Interface |
|--------|-----------|--------------|-----------|
| HS-CORE-FW1 | G1/7 | HS-CORE-R1 | G0/0 |

---

## 🧠 IP Addressing Plan (Point-to-Point)

| Link Name | Network | Subnet Mask | Usable IPs |
|----------|---------|-------------|------------|
| HS-CORE-FW1 ↔ HS-CORE-R1 | 10.255.255.0/30 | 255.255.255.252 | 10.255.255.1 – 10.255.255.2 |

---

## 📌 Interface IP Assignments

| Device | Interface | Description | IP Address / Mask |
|--------|-----------|-------------|-------------------|
| HS-CORE-FW1 | Gi1/7 | To-HS-CORE-R1 | 10.255.255.1 /30 |
| HS-CORE-R1 | Gi0/0 | To-HS-CORE-FW1 | 10.255.255.2 /30 |

---

## ⚙️ Configuration Summary (High-Level)

Use these steps on each device (do not repeat commands line-by-line):

| Device | What to Do |
|--------|------------|
| HS-CORE-FW1 | Enter interface **Gi1/7**, add a description, assign the IP, and enable the interface |
| HS-CORE-R1 | Enter interface **Gi0/0**, add a description, assign the IP, and enable the interface |

---
