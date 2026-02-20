# 🌐 01 – Test Floor1 to Floor3 DNS Resolution

##  Overview

This test validates DNS service functionality for user endpoints on Floor 1, Floor 2, and Floor 3.

The objective is to confirm:
- Correct DNS server assignment via DHCP
- Successful domain name resolution
- External DNS server reachability

## Reference Topology

<img width="784" height="639" alt="topology" src="https://github.com/user-attachments/assets/5e8733fb-7ee1-4ac0-b0b5-9877d5e5b8fc" />

---

## Endpoints Tested

| Floor | Department | VLAN | Subnet | Test PC | IP Address | Addressing Method |
|-------|------------|------|--------|---------|------------|------------------|
| 1 | Emergency | 101 | 172.16.1.0/26 | ED-1 | 172.16.1.4 | DHCP |
| 2 | Medical Records | 200 | 172.16.2.0/27 | MRD-1 | 172.16.2.4 | DHCP |
| 3 | Radiology | 330 | 172.16.3.128/26 | Rad-1 | 172.16.3.133 | DHCP |

---


## Test Procedure

On each endpoint:

1. Open **Command Prompt**
2. Run the following commands:

### On ED-1 nslookup google.com and nslookup youtube.com

<img width="730" height="438" alt="1" src="https://github.com/user-attachments/assets/c093038c-b19b-4243-ae67-fcb4eea6bcdc" />

### On MRD-1 nslookup google.com and nslookup youtube.com

<img width="731" height="438" alt="2" src="https://github.com/user-attachments/assets/248619af-1f5c-4014-879c-a0f21861e296" />

### On Rad-1 nslookup google.com and nslookup youtube.com

<img width="734" height="440" alt="3" src="https://github.com/user-attachments/assets/2e71b593-ed5b-4795-b6e8-0767d2c8e301" />
