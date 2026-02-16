# 🌐 06 – ISP1 to Hospital Connection

This document describes the **WAN connection between ISP1 and the hospital network**.  
The connection provides external internet access to the hospital.

---

## 📌 Connection Overview

The hospital connects to **ISP1** through the **core firewall** using a point-to-point /30 network.

- ISP Router: **ISP1-R1**
- Hospital Edge Devices: **HS-EDGE-R1 and HS-EDGE-R2**
- Connection Type: **Fiber**
- Addressing: **Static IP addressing**

---

| Device | Interface | Connected To | Interface |
|------|-----------|--------------|-----------|
| ISP1-R1 | G1/1/1 | HS-EDGE-R1 | G1/1/1 |
| ISP1-R1 | G1/1/2 | HS-EDGE-R1 | G1/1/2 |
| ISP1-R1 | G1/1/3 | HS-EDGE-R2 | G1/1/1 |
| ISP1-R1 | G1/1/4 | HS-EDGE-R2 | G1/1/2 |

---

## 🌍 WAN IP Addressing

| Device | Interface | IP Address | Subnet Mask | Network |
|------|-----------|------------|-------------|---------|
| ISP1-R1 | Po15 | 69.45.12.1 | 255.255.255.252 | 69.45.12.0/30 |
| HS-EDGE-R1 | Po15 | 69.45.12.2 | 255.255.255.252 | 69.45.12.0/30 |
| ISP1-R1 | Po10 | 100.45.12.1 | 255.255.255.252 | 100.45.12.0/30 |
| HS-EDGE-R2 | Po15 | 100.45.12.2 | 255.255.255.252 | 100.45.12.0/30 |

--- 

## Reference Diagram

<img width="656" height="309" alt="toplogy" src="https://github.com/user-attachments/assets/537ffd1a-d9d6-4c81-9758-98f69abc88d1" />

## ✅ Verification

### On ISP1-R1: show ip interface brief | include Port

<img width="766" height="99" alt="ISP1-R1" src="https://github.com/user-attachments/assets/5bf94113-6b8b-4b2e-9d0a-d65f1a80773a" />
