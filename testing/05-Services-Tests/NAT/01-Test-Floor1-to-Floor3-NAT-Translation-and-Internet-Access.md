# 🌐 01 – Test Floor1 to Floor3 NAT Translation and Internet Access

##  Overview

This test validates Network Address Translation functionality for endpoints on Floor 1, Floor 2, and Floor 3.

## Reference Topology

<img width="784" height="639" alt="topology" src="https://github.com/user-attachments/assets/5e8733fb-7ee1-4ac0-b0b5-9877d5e5b8fc" />

The objective is to confirm:

- Internal private IP addresses are translated to public IP addresses
- Endpoints can reach ISP external addresses
- NAT translations are created dynamically

I used 1 endpoint per floor to validate NAT functionality on each floor.

---

## Endpoints Tested

| Floor | Department | VLAN | Subnet | Test PC | IP Address | Addressing Method |
|-------|------------|------|--------|---------|------------|------------------|
| 1 | Emergency | 101 | 172.16.1.0/26 | ED-1 | 172.16.1.4 | DHCP |
| 2 | Medical Records | 200 | 172.16.2.0/27 | MRD-1 | 172.16.2.4 | DHCP |
| 3 | Radiology | 330 | 172.16.3.128/26 | Rad-1 | 172.16.3.133 | DHCP |

---

