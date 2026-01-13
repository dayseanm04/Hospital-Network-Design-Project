# 🌐 06 – Update DHCP Pools to Match HSRP Virtual IP

After configuring **HSRP** on the access switches, I will update the **DHCP pools** so clients receive the **HSRP Virtual IP (VIP)** as their **default gateway**.  
This ensures end devices continue to work correctly during gateway failover.


## 🎯 Objective

- ✅ Update DHCP **default gateway** to use the HSRP **VIP**
- ✅ Adjust DHCP **starting IP address** to avoid conflicts

---

## 🧠 Why This Is Required

With HSRP, hosts must use the **virtual IP**, not a SVI IP of the VLANs.

If DHCP is not updated, clients may:
- Point to the wrong gateway
- Lose connectivity during failover

---

## 🏥 Floor 1 - DHCP Updates

| VLAN | Department | HSRP VIP (Default GW) | DHCP Start IP |
|---:|---|---|---|
| 101 | Emergency DPT | 172.16.1.3 | 172.16.1.4 |
| 110 | X-Ray DPT | 172.16.1.67 | 172.16.1.68 |
| 120 | Nurse Stations | 172.16.1.99 | 172.16.1.100 |

---
