# Configure PAT on HS-EDGE-R1 for ISP1

## Overview

This task, I will configures **PAT (NAT Overload)** on **HS-EDGE-R1** to translate internal hospital networks to public IP addresses from the **ISP1 NAT pool**.

PAT allows multiple internal hosts to share a limited number of public IP addresses.

## Reference Topology

<img width="784" height="639" alt="topology" src="https://github.com/user-attachments/assets/5e8733fb-7ee1-4ac0-b0b5-9877d5e5b8fc" />

---

## Objective
- Create ACL for internal networks to be translated
- Configure NAT inside/outside interfaces
- Configure NAT pool for ISP1

---

## Step 1 – Create ACL for NAT Translation

```bash
ip access-list standard Translate-NAT
 10 permit 172.16.1.0 0.0.0.255
 20 permit 172.16.2.0 0.0.0.255
 30 permit 172.16.3.0 0.0.0.255
 40 permit 10.50.50.0 0.0.0.63
 50 deny any
```

Note: This translates Floor1 - 3 and the IT Department. It dosent translate the IP for the internal servers in the Server VLAN (10.10.10.0/27).

Also note that I made the sequence number increase by 10 so that I can insert new ACL entries when necessary.

## Step 2 – Configure NAT Interfaces

In Global Config mode:

```bash
interface Port-channel15
 ip nat outside

interface Port-channel1
 ip nat inside
```

Note: Port-Channel 15 is the connection to ISP1 and Port-Channel 1 is the connection to HS-CORE-FW1

## Step 3 – Configure NAT Pool (ISP1)

In Global Config mode:

```bash
ip nat pool ISP1-Pool 100.100.100.1 100.100.100.2 netmask 255.255.255.252
```

Note:
- The public IP range is 100.100.100.1 – 100.100.100.2
- The total usable IPs is 2

## Step 4 – Enable PAT (Overload)

In Global Config mode:

```bash
ip nat inside source list Translate-NAT pool ISP1-Pool overload
```

## Verification

```bash
show ip nat statistics
```

<img width="763" height="242" alt="HS-EDGE-R1" src="https://github.com/user-attachments/assets/4c75a7d7-b57c-4d1e-8f21-3828ab5d0697" />
