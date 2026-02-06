# 🌐 Configure INET Servers IP Addresses

In this task, I will configure the **INET Srvers** IP addresses 

This network represents external Internet services that the **hospital network accesses through ISP1**.

## 🎯 Objectives

- ✅ Build the INET services LAN
- ✅ Assign **static IP addresses** to Internet service servers
- ✅ Configure hostnames and interface descriptions


## Topology For Reference

<img width="745" height="301" alt="reference-topology" src="https://github.com/user-attachments/assets/efe4388b-2f59-4b9e-851a-c135db1689ad" />


---

## 🧠 Network Overview

| Device | Role |
|---|---|
| `ISP1-R1` | ISP L3 Switch providing access to INET services |
| `INET-SW` | Switch for INET services network |
| `DNS-SRV` | Internet DNS server |
| `HTTP-SRV` | Internet Web server |
| `NTP-SRV` | Internet NTP server |
| `INET-PC1` | Test client |

**INET Services Subnet:** `10.20.20.0/24`


## 🖥️ INET Servers interfaces on INET-SW

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
ping 10.20.20.11
ping 10.20.20.12
```

**The Ping were successful✅**

<img width="894" height="380" alt="Ping-Test" src="https://github.com/user-attachments/assets/239dc049-0429-4703-965b-dc0b5b40e13b" />
