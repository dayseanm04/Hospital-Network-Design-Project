# 🌐 02 – Configure INET Services Network

In this task, I will configure the INET services network behind the INET edge router so the hospital network can access Internet services through ISP1. 

This includes configuring the LAN-facing interface, assigning static IP addresses to the servers, and setting basic device identity such as hostnames and interface descriptions.

## 🎯 Objectives

- ✅ Configure the INET router interface connected to `INET-SW`
- ✅ Configure static IP addresses to Internet service servers
- ✅ Configure hostnames
- ✅ Add interface descriptions for documentation and troubleshooting

## Reference INET

<img width="1130" height="292" alt="INET" src="https://github.com/user-attachments/assets/f19c68e4-e376-4cf7-bbd9-e6a73d31e806" />

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
interface g0/0/0
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
| `INET-PC1` | 10.20.20.200 | 255.255.255.0 | 10.20.20.1      |


## 🔌 INET Servers and End Devices – Switch Connections

| Device | Role | Switch | Switch Interface |
|---|---|---|---|
| DNS-SRV | DNS Server | INET-SW | G1/0/1 |
| HTTP-SRV | Web Server | INET-SW | G1/0/2 |
| NTP-SRV | NTP Server | INET-SW | G1/0/3 |
| INET-PC1 | Test Client | INET-SW | G1/0/5 |
