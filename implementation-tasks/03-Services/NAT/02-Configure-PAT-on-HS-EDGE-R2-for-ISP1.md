# 🌐 Configure PAT on HS-EDGE-R2 for ISP1

## 📌 Overview

This task, I will configures **PAT (NAT Overload)** on **HS-EDGE-R2** to translate internal hospital networks to public IP addresses from the **ISP2 NAT pool**.

PAT allows multiple internal hosts to share a limited number of public IP addresses.

## Reference Topology

<img width="784" height="639" alt="topology" src="https://github.com/user-attachments/assets/5e8733fb-7ee1-4ac0-b0b5-9877d5e5b8fc" />


## 🎯 Objectives
- Create ACL for internal networks to be translated
- Configure NAT inside/outside interfaces
- Configure NAT pool for ISP2

---

## 🧾 Step 1 – Create ACL for NAT Translation

```bash
ip access-list standard Translate-NAT
 1 permit 172.16.1.0 0.0.0.255
 2 permit 172.16.2.0 0.0.0.255
 3 permit 172.16.3.0 0.0.0.255
 4 permit 10.50.50.0 0.0.0.63
 5 deny any
```

Note: This translates Floor1 - 3 and the IT Department. It dosent translate the IP for the internal servers in the Server VLAN (10.10.10.0/27)

## 🔧 Step 2 – Configure NAT Interfaces

In Global Config mode:

```bash
interface Port-channel15
 ip nat outside

interface Port-channel1
 ip nat inside
```

Note: Port-Channel 15 is the connection to ISP2 and Port-Channel 1 is the connection to HS-CORE-FW2

## 🌍 Step 3 – Configure NAT Pool (ISP1)

In Global Config mode:

```bash
ip nat pool ISP1-Pool2 200.200.200.1 200.200.200.2 netmask 255.255.255.252
```

Note:
- The public IP range is 200.100.100.1 – 200.100.100.2
- The total usable IPs is 2

## 🔁 Step 4 – Enable PAT (Overload)

In Global Config mode:

```bash
ip nat inside source list Translate-NAT pool ISP1-Pool2 overload
```

## 🔍 Verification

```bash
show ip nat statistics
```

<img width="726" height="242" alt="HS-EDGE-R2" src="https://github.com/user-attachments/assets/fe7560af-78e5-4c86-8abc-571ab60591e1" />

