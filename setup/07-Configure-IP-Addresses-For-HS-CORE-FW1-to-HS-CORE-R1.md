# 🌐 Configure IP addresses for HS-CORE-FW1 ↔ HS-CORE-R1

This document covers the point-to-point Layer 3 connection between the **Hospital Core Firewall (HS-CORE-FW1)** and 
the **Hospital Core Router (HS-CORE-R1)**.

✅ I used a **private IP subnet** for this link because it is an internal connection.  
📌 **Note:** Dynamic routing is **not configured yet** in this phase.

---

## 🔗 Physical Connection

| Device | Interface | Connected To | Interface |
|--------|-----------|--------------|-----------|
| HS-CORE-FW1 | Gi1/7 | HS-CORE-R1 | Gi0/0 |


