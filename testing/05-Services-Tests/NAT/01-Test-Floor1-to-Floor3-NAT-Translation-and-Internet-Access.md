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

## 🧪 Test Procedure

###  Step 1 - Verify Public Reachability

From each endpoint (ED-1, MRD-1, Rad-1):

### On ED-1 ping 69.45.12.1 and ping 100.45.12.1

<img width="857" height="615" alt="2" src="https://github.com/user-attachments/assets/ec889185-fe03-4c80-a20f-5dd06272fe95" />

### On MRD-1 ping 69.45.12.1 and ping 100.45.12.1

<img width="733" height="612" alt="3" src="https://github.com/user-attachments/assets/a995a6b1-1487-4dac-9c85-654172c22524" />











