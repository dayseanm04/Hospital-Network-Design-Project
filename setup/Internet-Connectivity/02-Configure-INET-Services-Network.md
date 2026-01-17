# 🌐 02 – Configure INET Services Network

In this task, I will configure the INET services network behind the INET edge router so the hospital network can access Internet services through ISP1. 

This includes configuring the LAN-facing interface, assigning static IP addresses to the servers, and setting basic device identity such as hostnames and interface descriptions.

## 🎯 Objectives

- ✅ Configure the INET router interface connected to `INET-SW`
- ✅ Configure static IP addresses to Internet service servers
- ✅ Configure hostnames
- ✅ Add interface descriptions for documentation and troubleshooting

## Reference INET

<img width="1156" height="302" alt="INET" src="https://github.com/user-attachments/assets/24a28233-08b2-41f2-adc5-827166b06c5d" />

---

## 🧠 INET Services Network Overview

| INET | Details |
|---|---|
| `INET-Edge-01` | INET edge router (connects services to ISP1) |
| `INET-SW` | Switch for INET services network |
| `DNS-SRV` | DNS server |
| `HTTP-SRV` | Web server |
| `NTP-SRV` | Time server |

**INET Services Subnet:** `10.20.20.0/24`

---

## 🌐 INET Router LAN Interface Configuration

#### ♦️ Configure INET-EDGE G0/0 interface connected to `INET-SW` (Server LAN):

```bash
interface g0/0
```

#### ♦️ Configure IP

```bash
ip address 10.20.20.1 255.255.255.0
no shutdown
```

## 🖥️ INET Services Server IP Addressing (Static)

| Server     | IP Address  | Subnet Mask   | Default Gateway |
| ---------- | ----------- | ------------- | --------------- |
| `DNS-SRV`  | 10.20.20.10 | 255.255.255.0 | 10.20.20.1      |
| `HTTP-SRV` | 10.20.20.11 | 255.255.255.0 | 10.20.20.1      |
| `NTP-SRV`  | 10.20.20.12 | 255.255.255.0 | 10.20.20.1      |
