# 🌐 Configure INET Services Network Behind ISP1

In this task, I will configure the **INET services network** that sits **behind ISP1**.  

This network represents external Internet services that the **hospital network accesses through ISP1**.

## 🎯 Objectives

- ✅ Configure the ISP1 interface connected to the INET network
- ✅ Build the INET services LAN
- ✅ Assign **static IP addresses** to Internet service servers
- ✅ Configure hostnames and interface descriptions


## Topology For Reference

<img width="746" height="328" alt="INET" src="https://github.com/user-attachments/assets/50ef5b6d-db82-477d-9ab8-f33c2bd1bd8c" />

---

## 🧠 Network Overview

| Device | Role |
|---|---|
| `ISP1-R1` | ISP router providing access to INET services |
| `INET-SW` | Switch for INET services network |
| `DNS-SRV` | Internet DNS server |
| `HTTP-SRV` | Internet Web server |
| `NTP-SRV` | Internet NTP server |
| `INET-PC1` | Test client |

**INET Services Subnet:** `10.20.20.0/24`

---

## 🌐 ISP1 – INET LAN Interface Configuration

Configure the ISP1 router interface connected to `INET-SW` G1/1/1 interface.

```bash
interface g6/0
```

#### 🟢 Configure IP

```bash
ip address 10.20.20.1 255.255.255.0
```

#### 🟢 Enable the Interface

```bash
no shutdown
```

---

| Device   | Role        | Switch  | Switch Interface |
| -------- | ----------- | ------- | ---------------- |
| DNS-SRV  | DNS Server  | INET-SW | G1/0/1           |
| HTTP-SRV | Web Server  | INET-SW | G1/0/2           |
| NTP-SRV  | NTP Server  | INET-SW | G1/0/3           |
| INET-PC1 | Test Client | INET-SW | G1/0/5           |


## 🖥️ Static IP Addressing for INET Servers

| Device   | IP Address  | Subnet Mask   | Default Gateway |
| -------- | ----------- | ------------- | --------------- |
| DNS-SRV  | 10.20.20.10 | 255.255.255.0 | 10.20.20.1      |
| HTTP-SRV | 10.20.20.11 | 255.255.255.0 | 10.20.20.1      |
| NTP-SRV  | 10.20.20.12 | 255.255.255.0 | 10.20.20.1      |
| INET-PC1 | 10.20.20.200 | 255.255.255.0 | 10.20.20.1      |

## 🔍 Verification

#### From ISP1-R1, verify connectivity to INET server:

```bash
ping 10.20.20.10
ping 10.20.20.20
ping 10.20.20.30
```

**The Ping were successful✅**

<img width="894" height="380" alt="Ping-Test" src="https://github.com/user-attachments/assets/239dc049-0429-4703-965b-dc0b5b40e13b" />






