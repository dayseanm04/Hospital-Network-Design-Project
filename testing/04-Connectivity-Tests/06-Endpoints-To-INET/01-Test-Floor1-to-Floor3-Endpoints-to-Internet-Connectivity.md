# 🌐 01 – Test Floor1 to Floor3 Endpoints to Internet Connectivity

## 📌 Overview

This test verifies that endpoints from Floor 1, Floor 2, and Floor 3 can successfully access external internet resources.

The goal is to validate:

- Hosptial LAN can reach the internet
- DNS resolution
- OSPF route propagation

I only used one endpoint per floor is used for validation, I confirmed that every PC can access the internet access.

## Reference Topology

<img width="784" height="639" alt="topology" src="https://github.com/user-attachments/assets/5e8733fb-7ee1-4ac0-b0b5-9877d5e5b8fc" />

---


## 🏢 Endpoints Tested

| Floor | Department | VLAN | Subnet | Test PC | IP Address | Addressing Method |
|-------|------------|------|--------|---------|------------|------------------|
| 1 | Emergency | 101 | 172.16.1.0/26 | ED-1 | 172.16.1.4 | DHCP |
| 2 | Medical Records | 200 | 172.16.2.0/27 | MRD-1 | 172.16.2.4 | DHCP |
| 3 | Radiology | 330 | 172.16.3.128/26 | Rad-1 | 172.16.3.133 | DHCP |

---

## 🧪 Test Procedure

On each endpoint:

1. Open **Command Prompt**
2. Run the following commands:

On ED1 ping google.com and ping youtube.com

<img width="877" height="425" alt="1" src="https://github.com/user-attachments/assets/cf739d50-5454-4c33-babf-abe93de075a7" />

















