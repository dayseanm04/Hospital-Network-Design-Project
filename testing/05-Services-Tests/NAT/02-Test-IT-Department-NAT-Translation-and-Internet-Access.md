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

<img width="817" height="655" alt="1" src="https://github.com/user-attachments/assets/3d840e5d-e304-4600-83d4-af08c88edca3" />

### On IT-PC2 ping 69.45.12.1 and ping 100.45.12.1

<img width="797" height="606" alt="2" src="https://github.com/user-attachments/assets/cdd54914-87ad-4cca-ab2c-beb2d26e7189" />

###  Step 2 - Verify NAT Translations

On the edge router (HS-EDGE-R2), run:

```bash
show ip nat translations
```

<img width="781" height="136" alt="1" src="https://github.com/user-attachments/assets/5b708228-c65c-4c23-bbe9-00d458cc6867" />


