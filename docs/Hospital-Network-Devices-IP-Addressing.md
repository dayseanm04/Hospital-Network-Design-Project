# 🌐 Network Devices IP Addressing Table

This document contains the **IP addresses used by all network devices** in the Hospital Network Design project.

The information is grouped by **network layer** and **type of connection** so it is easy to read, update, and troubleshoot as the network expands.

---

## 🧱 Core Layer

### 🌍 ISP ↔ Core Firewall

| Connection | Interface | IP Address | Network | Notes |
|-----------|----------|-----------|--------|------|
| ISP1-R1 → HS-CORE-FW1 | ISP1-R1 G9/0 | 69.45.12.1 /30 | 69.45.12.0 /30 | |
| ISP1-R1 → HS-CORE-FW1 | HS-CORE-FW1 G1/08 | 69.45.12.2 /30 | 69.45.12.0 /30 | |

---

### 🔐 Core Firewall ↔ Core Router

| Connection | Interface | IP Address | Network | Notes |
|-----------|----------|-----------|--------|------|
| HS-CORE-FW1 → HS-CORE-R1 | HS-CORE-FW1 G1/07 | 10.255.255.1 /30 | 10.255.255.0 /30 | |
| HS-CORE-FW1 → HS-CORE-R1 | HS-CORE-R1 G0/0 | 10.255.255.2 /30 | 10.255.255.0 /30 | |

---
