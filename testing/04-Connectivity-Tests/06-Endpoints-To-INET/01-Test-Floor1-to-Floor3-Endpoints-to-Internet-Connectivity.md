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

### On ED-1 ping google.com and ping youtube.com

<img width="877" height="425" alt="1" src="https://github.com/user-attachments/assets/cf739d50-5454-4c33-babf-abe93de075a7" />

<img width="873" height="424" alt="2" src="https://github.com/user-attachments/assets/7ba1fb95-dfad-491f-b0a3-415bd073c3e6" />


### On MRD-1 ping google.com and ping youtube.com

<img width="731" height="364" alt="3" src="https://github.com/user-attachments/assets/cf260ba6-15f7-4faa-ae09-3b0377df0ceb" />

<img width="730" height="367" alt="4" src="https://github.com/user-attachments/assets/349c2e68-98d4-46be-93fe-316714754f9b" />


### On Rad-1 ping google.com and ping youtube.com

<img width="728" height="352" alt="5" src="https://github.com/user-attachments/assets/56861152-2460-402a-9466-91445cac62bf" />

<img width="737" height="360" alt="6" src="https://github.com/user-attachments/assets/3a4231d1-db24-436d-bcb6-5a77cf9da5d8" />
