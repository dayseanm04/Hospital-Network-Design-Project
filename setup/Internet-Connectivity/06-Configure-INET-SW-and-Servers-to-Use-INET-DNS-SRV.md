# 🌐 06 – Configure INET-SW and Servers to Use INET-DNS-SRV

## 📌 Overview

In this task, I will configure the INET servers devices to use the INET-DNS server:
DNS Server IP: 10.20.20.10

This ensures proper name resolution across INET.

## Reference Topology

<img width="835" height="325" alt="toplogy" src="https://github.com/user-attachments/assets/fb3d5afb-915a-4c7e-b5b0-c7f570012f61" />


## 🎯 Objective
- Configure INET-SW to use the INET-DNS-SRV
- Configure all INET servers to use INET-DNS-SRV
- Configure domain name for INET-SW and ISP1-R1
- Verify DNS configuration

---

## 🔧 Configure DNS on INET-SW

On INET-SW, Configure domain name:

```bash
ip domain-name inet.com
```

Configure DNS name:

```bash
ip name-server 10.20.20.10
```

📝 Purpose: Allows INET-SW to resolve domain names using the INET DNS Server.

## 🖥 Configure DNS on INET Servers

For each INET server:

- Click on the server
- Go to Config
- Enter the following under DNS Server: **`10.20.20.10`**

## 🔍 Verification

#### On INET-SW show hosts


#### On INET-WEB-SRV ipconfig /all

<img width="927" height="452" alt="WEB" src="https://github.com/user-attachments/assets/ac09e13f-b23d-47e9-bff1-adde2b2225cc" />

#### On INET-NTP-SRV ipconfig /all

<img width="910" height="471" alt="NTP" src="https://github.com/user-attachments/assets/abd122ed-1600-4877-a8fa-3f7cd4f77ee5" />

#### On INET-DNS-SRV ipconfig /all

<img width="896" height="434" alt="DNS" src="https://github.com/user-attachments/assets/98aae550-ef41-4370-a6cf-47fada4718cd" />
