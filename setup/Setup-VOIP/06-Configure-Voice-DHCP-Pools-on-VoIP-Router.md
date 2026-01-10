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


## Reference Network Diagram

<img width="796" height="371" alt="network-diagram" src="https://github.com/user-attachments/assets/dd71e4be-7333-47d1-8a96-ef3657dc1e92" />

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

### 🏥 IT-DPT Voice VLAN

```bash
ip dhcp pool IT-DPT-Voice
network 172.16.60.0 255.255.255.224
default-router 172.16.60.1
domain-name hospital.daysean.com
option 150 ip 10.0.0.13
```

## Verify

### on VOIP-Router

#### 🟢 show ip dhcp pool

<img width="824" height="472" alt="VOIP-R-dhcp-pool" src="https://github.com/user-attachments/assets/3a2742d1-0c65-4167-a5d7-a59d1cc53893" />

<img width="849" height="429" alt="VOIP-R-dhcp-pool-2" src="https://github.com/user-attachments/assets/c2790a89-b51c-46d4-a457-5fc105694ec8" />
