# 🌐 03 – Update NAT ACL to Exclude Printer IP Addresses

## 📌 Overview

Earlier, the **Translate-NAT** ACL I configured permitted entire /24 network for NAT translation.  
This means that printers IP addresses to be translated by NAT.

In this task  I will:
- Exclude printer IP addresses from NAT translation
- Apply updates on both edge routers (HS-EDGE-R1 & HS-EDGE-R2)

PAT allows multiple internal hosts to share a limited number of public IP addresses.

## Reference Topology

<img width="784" height="639" alt="topology" src="https://github.com/user-attachments/assets/5e8733fb-7ee1-4ac0-b0b5-9877d5e5b8fc" />

---

## Printer IP Addresses to Exclude

###  Floor 1
- ED-PRNT → 172.16.1.31
- X-R-PRNT → 172.16.1.80
- Nrs-PRNT → 172.16.1.120

### Floor 2
- M-PRNT → 172.16.2.20
- Fin-PRNT → 172.16.2.50
- HR-PRNT → 172.16.2.80

###  Floor 3
- N3-PRNT → 172.16.3.30
- Rad-PRNT → 172.16.3.140

---

### Configuration Steps for HS-EDGE-R1 and HS-EDGE-R2  

In Global Config mode:

### Configure Host-Level Deny Entries

```bash
ip access-list standard Translate-NAT
1 deny host 172.16.1.31
2 deny host 172.16.1.80
3 deny host 172.16.1.120
4 deny host 172.16.2.20
5 deny host 172.16.2.50
6 deny host 172.16.2.80
7 deny host 172.16.3.30
8 deny host 172.16.3.140
```
