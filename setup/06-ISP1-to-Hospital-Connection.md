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
| HS-CORE-FW1 | Po15 | 69.45.12.2 | 255.255.255.252 | 69.45.12.0/30 |

--- 

## Reference Diagram

<img width="807" height="314" alt="topology" src="https://github.com/user-attachments/assets/c862c60c-5e92-4b01-ac71-5320c72c7576" />


## ✅ Verification

### On ISP1-R1: show ip interface brief

<img width="860" height="97" alt="ISP1-PC" src="https://github.com/user-attachments/assets/abe0d5e8-e1d5-4c57-b55c-a8f36607cc59" />

### On HS-CORE-FW1: show ip address

<img width="871" height="119" alt="HS-CORE-FW-PC" src="https://github.com/user-attachments/assets/6fde1ee7-45b7-4453-a657-3e7c56e4a9ca" />
