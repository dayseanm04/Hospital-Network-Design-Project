# 🌐 02 – Test IT Department Endpoints to Internet Connectivity

## Overview

This test verifies that IT Department endpoints can successfully access external internet resources.

The objective is to validate:

- Hosptial LAN can reach the internet
- DNS resolution

The IT-DPT endpoints use **static IP addressing**, unlike other departments that use DHCP.

## Reference Topology

<img width="784" height="639" alt="topology" src="https://github.com/user-attachments/assets/5e8733fb-7ee1-4ac0-b0b5-9877d5e5b8fc" />


---

## Endpoints Tested

| Device | Department | VLAN | IP Address | Addressing Method |
|--------|------------|------|------------|------------------|
| IT-PC1 | IT | IT VLAN | 10.50.50.2 | Static |
| IT-PC2 | IT | IT VLAN | 10.50.50.3 | Static |

---

## Test Procedure

On each IT PC:

1. Open **Command Prompt**
2. Run the following commands:

### On IT-PC1 ping google.com and ping youtube.com

<img width="913" height="661" alt="1" src="https://github.com/user-attachments/assets/a9413385-787b-40cb-b03b-bed420c290ca" />

### On IT-PC2 ping google.com and ping youtube.com

<img width="920" height="645" alt="2" src="https://github.com/user-attachments/assets/e709e8b6-26e9-494b-a6ff-4bf68544a22d" />
