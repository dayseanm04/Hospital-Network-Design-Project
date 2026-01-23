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
| ISP1-R1 | G1/1/1 | HS-CORE-FW1 | Gi1/8 |
| ISP1-R1 | G1/1/2 | HS-CORE-FW1 | Gi1/6 |

---

## 🌍 WAN IP Addressing

| Device | Interface | IP Address | Subnet Mask | Network |
|------|-----------|------------|-------------|---------|
| ISP1-R1 | Po15 | 69.45.12.1 | 255.255.255.252 | 69.45.12.0/30 |
| HS-CORE-FW1 | Po15 | 69.45.12.2 | 255.255.255.252 | 69.45.12.0/30 |

--- 

## Reference Diagram

<img width="807" height="314" alt="topology" src="https://github.com/user-attachments/assets/c862c60c-5e92-4b01-ac71-5320c72c7576" />


## ✅ Verification

### On ISP1-R1: show ip interface brief

<img width="818" height="227" alt="ISP1-R1-verify-ip" src="https://github.com/user-attachments/assets/0c30afa9-1082-4d4d-8d66-d9914cad45ca" />

### On HS-CORE-FW1: show ip address

<img width="831" height="229" alt="HS-CORE-FW-verify-ip" src="https://github.com/user-attachments/assets/4d9c47f4-3311-4298-9860-663f4e6ba231" />



