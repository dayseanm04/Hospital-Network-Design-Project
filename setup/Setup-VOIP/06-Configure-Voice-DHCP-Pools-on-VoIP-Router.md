# 📞 Configure-Voice-DHCP-Pools-on-VoIP-Router

## 📌 Overview

In this task I will configure **DHCP pools for all Voice VLANs** on the **VoIP Router**.  

The DHCP service assigns IP addresses to **IP phones** and provides **Option 150**, which points phones to the **TFTP/Call Manager (telephony-service)**.

---

## 🧠 Key Notes

- **DHCP Server:** VoIP Router
- **Clients:** IP Phones (Voice VLANs)
- **Option 150:** Used by IP phones to locate the telephony-service
- **Telephony-Service IP:** `10.0.0.13` (VOIP Router Loopback)

---

## 🚫 Exclude Gateway IP Addresses

Exclude the SVI gateway addresses so they are **not assigned to phones**.

### ♦️ In Global config mode on VOIP-Router:

```bash
ip dhcp excluded-address 172.16.10.1
ip dhcp excluded-address 172.16.20.1
ip dhcp excluded-address 172.16.30.1
ip dhcp excluded-address 172.16.60.1
```

## Configure 📦 Voice DHCP Pools

### 🏢 F1 Voice VLAN Pool

```bash
ip dhcp pool F1-Voice
network 172.16.10.0 255.255.255.128
default-router 172.16.10.1
domain-name hospital.daysean.com
option 150 ip 10.0.0.13
```

### 🏢 F2 Voice VLAN Pool

```bash
ip dhcp pool F2-Voice
network 172.16.20.0 255.255.255.128
default-router 172.16.20.1
domain-name hospital.daysean.com
option 150 ip 10.0.0.13
```

### 🏢 F3 Voice VLAN Pool

```bash
ip dhcp pool F3-Voice
network 172.16.30.0 255.255.255.128
default-router 172.16.30.1
domain-name hospital.daysean.com
option 150 ip 10.0.0.13
```















