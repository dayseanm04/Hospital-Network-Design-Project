# 🌐 06 – ISP1 to Hospital Connection

This document describes the **WAN connection between ISP1 and the hospital network**.  
The connection provides external internet access to the hospital.

---

## 📌 Connection Overview

The hospital connects to **ISP1** through the **core firewall** using a point-to-point /30 network.

- ISP Router: **ISP1-R1**
- Hospital Edge Device: **HS-CORE-FW1**
- Connection Type: **Ethernet**
- Addressing: **Static IP addressing**

---

| Device | Interface | Connected To | Interface |
|------|-----------|--------------|-----------|
| ISP1-R1 | Gi9/0 | HS-CORE-FW1 | Gi1/8 |

---

## 🌍 WAN IP Addressing

| Device | Interface | IP Address | Subnet Mask | Network |
|------|-----------|------------|-------------|---------|
| ISP1-R1 | Gi9/0 | 69.45.12.1 | 255.255.255.252 | 69.45.12.0/30 |
| HS-CORE-FW1 | Gi1/8 | 69.45.12.2 | 255.255.255.252 | 69.45.12.0/30 |

--- 

