# 🌐 Configure PAT on HS-EDGE-R1 for ISP1

## 📌 Overview

This task, I will configures **PAT (NAT Overload)** on **HS-EDGE-R1** to translate internal hospital networks to public IP addresses from the **ISP1 NAT pool**.

PAT allows multiple internal hosts to share a limited number of public IP addresses.

## Reference Topology

<img width="784" height="639" alt="topology" src="https://github.com/user-attachments/assets/5e8733fb-7ee1-4ac0-b0b5-9877d5e5b8fc" />

---

## 🎯 Objective
- Create ACL for internal networks to be translated
- Configure NAT inside/outside interfaces
- Configure NAT pool for ISP1

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

