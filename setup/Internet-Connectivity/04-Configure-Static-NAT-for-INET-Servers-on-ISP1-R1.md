# 🌐 Configure Static NAT for INET Servers on ISP1-R1

In this task, I configure static NAT on ISP1-R1 so that the INET servers (DNS, HTTP, and NTP) can be reached using public IP addresses. 

## 🎯 Objectives

- ✅ Configure **inside** and **outside** NAT interfaces on ISP1-R1
- ✅ Create **static NAT mappings** for INET servers
- ✅ Verify NAT translations and connectivity


## Topology For Reference

<img width="745" height="301" alt="reference-topology" src="https://github.com/user-attachments/assets/efe4388b-2f59-4b9e-851a-c135db1689ad" />

---

## 🧠 NAT Design Overview

- **Inside (private) network:** towards the INET network  `10.20.20.0/24`
- **Outside (public) network:** towards the hospital Edge Routers
- **NAT type:** Static

---

## 🔌 Interface Roles (ISP1-R1)

| Interface | Role |
|---|---|
| Interface toward `INET-SW` | `ip nat inside` |
| Interfaces toward `HS-EDGE-R1` | `ip nat outside` |
| Interfaces toward `HS-EDGE-R2` | `ip nat outside` |


---

## ⚙️ Configue ISP1-R1

🔶 In Global config mode

### 1️⃣ Configue NAT Interfaces

```bash
interface Port-channel1
 ip nat inside 
```

```bash
interface Port-channel15
 ip nat outside

interface Port-channel10
 ip nat outside 
```

### 2️⃣ Configure Static NAT Mappings

Create one-to-one mappings between private server IPs and public IPs.

```bash
ip nat inside source static 10.20.20.10 200.10.0.2
```

➡️ Maps INET DNS-SRV to the public IP.

```bash
ip nat inside source static 10.20.20.11 200.10.0.4
```

➡️ Maps INET WEB-SRV to the public IP.

```bash
ip nat inside source static 10.20.20.12 200.10.0.6
```

➡️ Maps INET WEB-SRV to the public IP.

```bash
ip nat inside source static 10.20.20.200 200.10.0.8
```

➡️ Maps INET NTP-SRV to the public IP.

## 🗂️ Static NAT Mapping Summary

| INET Server | Private IP  | Public IP  |
| ----------- | ----------- | ---------- |
| DNS-SRV     | 10.20.20.10 | 200.10.0.2 |
| HTTP-SRV    | 10.20.20.11 | 200.10.0.4 |
| NTP-SRV     | 10.20.20.12 | 200.10.0.6 |

## 🔍 Verification

### ♦️ show ip nat translations on ISP1-R1

<img width="807" height="135" alt="ISP1-NAT-TRANSLATIONS" src="https://github.com/user-attachments/assets/695c30dc-ab58-41c5-bf7b-e3e4160a5205" />

<br/>

Ping the Public IP of HS-CORE-FW1 from INET-DNS-SRV

<img width="708" height="376" alt="INET-DNS-SRV-ping-public-IP" src="https://github.com/user-attachments/assets/360ea5a9-56cb-4fc9-8ab9-0b2aa702d6a2" />

INET-DNS-SRV sucessfully ping HS-CORE-FW1 public IP

### ♦️ show ip nat translations on ISP1-R1 after ping

<img width="819" height="196" alt="ISP1-NAT-TRANSLATIONS-2" src="https://github.com/user-attachments/assets/f107927a-4b03-438f-a99a-40bd83dfbfcc" />




















