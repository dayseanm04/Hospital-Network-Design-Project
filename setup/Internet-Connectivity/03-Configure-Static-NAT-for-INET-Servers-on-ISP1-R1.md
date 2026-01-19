# 🌐 Configure Static NAT for INET Servers on ISP1-R1

In this task, I will configure **static NAT** on **ISP1-R1** for ther **INET servers** (DNS, HTTP, NTP) using **public IP addresses**. 

Static NAT provides fixed, predictable mappings so external clients can reliably reach INET services.

## 🎯 Objectives

- ✅ Configure **inside** and **outside** NAT interfaces on ISP1-R1
- ✅ Create **static NAT mappings** for INET servers
- ✅ Verify NAT translations and connectivity

## Topology For Reference

<img width="746" height="328" alt="INET" src="https://github.com/user-attachments/assets/50ef5b6d-db82-477d-9ab8-f33c2bd1bd8c" />

---

## 🧠 NAT Design Overview

- **Inside (private) network:** INET services subnet `10.20.20.0/24`
- **Outside (public) network:** ISP-facing links toward the hospital firewall
- **NAT type:** Static

---

## 🔌 Interface Roles (ISP1-R1)

| Interface | Role |
|---|---|
| G6/0 (Interface toward `INET-SW`) | `ip nat inside` |
| G8/0 and G9/0 (Interface toward `HS-CORE-FW1`) | `ip nat outside` |

> 💡 Marking interfaces correctly is required before creating NAT rules.

---

## ⚙️ Configuration Steps (ISP1-R1)

### 1️⃣ Configure NAT interfaces

### ♦️ In Global Config mode:

#### 🟢 Configure G6/0 as nat inside:

```bash
interface G6/0
ip nat inside
```

#### 🟢 Configure G8/0 and G9/0 as nat outisde:

```bash
interface G8/0
ip nat outside
```

```bash
interface G9/0
ip nat outside
```

## 2️⃣ Configure Static NAT Mappings

### 🔷 Create one-to-one mappings for INET servers.

<br/>

#### ♦️ Map INET-DNS-SRV to 200.10.0.2

```bash
ip nat inside source static 10.20.20.10 200.10.0.2
```

#### ♦️ Map INET-HTTP-SRV to 200.10.0.4

```bash
ip nat inside source static 10.20.20.11 200.10.0.4
```

#### ♦️ Map INET-NTP-SRV to 200.10.0.6

```bash
ip nat inside source static 10.20.20.12 200.10.0.6
```

## 🗂️ Static NAT Mapping Summary

| INET Server | Private IP  | Public IP  |
| ----------- | ----------- | ---------- |
| DNS-SRV     | 10.20.20.10 | 200.10.0.2 |
| HTTP-SRV    | 10.20.20.11 | 200.10.0.4 |
| NTP-SRV     | 10.20.20.12 | 200.10.0.6 |

## 🔍 Verification

### Ping HS-CORE-FW1 interface connected to ISPR1 from INET-DNS-SRV

```bash
ping 69.45.12.2
```
<img width="700" height="371" alt="DNS-SRV-ping-internet" src="https://github.com/user-attachments/assets/923716b6-d417-429e-b307-c5e217e63677" />

The ping was successful, 2 out of the 4 packers sent request times out, might be because of packet tracer.





































