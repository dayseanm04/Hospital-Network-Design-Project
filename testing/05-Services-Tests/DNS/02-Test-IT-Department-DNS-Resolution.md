# 🌐 02 – Test IT Department DNS Resolution

## Overview

This test validates DNS service functionality for IT Department endpoints.

Unlike other departments that receive IP configuration via DHCP, IT endpoints use **static IP addressing**.  
This test ensures that DNS resolution functions correctly for statically configured devices.

## Reference Topology

<img width="784" height="639" alt="topology" src="https://github.com/user-attachments/assets/5e8733fb-7ee1-4ac0-b0b5-9877d5e5b8fc" />

---

The objective is to confirm:

- Proper DNS server configuration on static endpoints
- Successful domain name resolution
- DNS server reachability

## Endpoints Tested

| Device | Department | VLAN | IP Address | Addressing Method |
|--------|------------|------|------------|------------------|
| IT-PC1 | IT | IT VLAN | 10.50.50.2 | Static |
| IT-PC2 | IT | IT VLAN | 10.50.50.3 | Static |

 
