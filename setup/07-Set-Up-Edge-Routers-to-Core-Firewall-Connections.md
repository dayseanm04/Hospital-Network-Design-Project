# 🔗 Set Up Edge Routers to Core Firewall Connections

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

## ⚙️ Configuration Summary

Use these steps on each device:

| Device | What to Do |
|--------|------------|
| HS-CORE-FW1 | Enter interface **Gi1/7**, add a description, assign the IP, and enable the interface |
| HS-CORE-R1 | Enter interface **Gi0/0**, add a description, assign the IP, and enable the interface |

---

## Reference Diagram

<img width="572" height="266" alt="HS1-CORE-FW1-HS-CORE-R1" src="https://github.com/user-attachments/assets/d06f39ac-f48d-4f12-a5d8-9212af1cd111" />


## ✅ Verification

### On HS-CORE-FW1: show ip address

<img width="833" height="224" alt="show-ip-address-hs-core-fw1" src="https://github.com/user-attachments/assets/9e381dc5-c2c7-4de0-aa53-259632c2959c" />

### On HS-CORE-R1: show ip address

<img width="826" height="115" alt="show-ip-address-hs-core-r1" src="https://github.com/user-attachments/assets/6e16cb8c-19ae-4f64-b840-32ed10bcdd55" />
