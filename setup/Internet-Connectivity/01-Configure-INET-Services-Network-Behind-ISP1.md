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



