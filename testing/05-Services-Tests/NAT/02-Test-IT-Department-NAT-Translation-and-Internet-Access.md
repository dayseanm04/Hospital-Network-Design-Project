# 🌐 02 – Test IT Department NAT Translation and Internet Access

##  Overview

This test validates NAT functionality for IT Department endpoints.

Unlike other departments that use DHCP, IT endpoints are configured with **static IP addresses**.  
This test ensures that devices with static IP Addresses are correctly being translated to public IP addresses and can access external networks.

## Reference Topology

<img width="784" height="639" alt="topology" src="https://github.com/user-attachments/assets/5e8733fb-7ee1-4ac0-b0b5-9877d5e5b8fc" />

The objective is to confirm:

- Static internal IP addresses are translated to public IP addresses
- IT endpoints can reach external ISP addresses
- Dynamic NAT translations are created on the edge router

---

## Endpoints Tested

| Device | Department | VLAN | IP Address | Addressing Method |
|---------|------------|------|------------|------------------|
| IT-PC1 | IT | IT DPT | 10.50.50.2 | Static |
| IT-PC2 | IT | IT DPT | 10.50.50.3 | Static |

---

## 🧪 Test Procedure

###  Step 1 - Verify External Networks Reachability

From IT-PC1 and IT-PC2, run:

### On IT-PC1 ping 69.45.12.1 and ping 100.45.12.1








