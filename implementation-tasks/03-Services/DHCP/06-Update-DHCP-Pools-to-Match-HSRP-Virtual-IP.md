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

## 🏥 Floor 1 - DHCP Update

| VLAN | Department | HSRP VIP (Default GW) | DHCP Start IP |
|---:|---|---|---|
| 101 | Emergency DPT | 172.16.1.3 | 172.16.1.4 |
| 110 | X-Ray DPT | 172.16.1.67 | 172.16.1.68 |
| 120 | Nurse Stations | 172.16.1.99 | 172.16.1.100 |

---

## 🏢 Floor 2 - DHCP Update

| VLAN | Department | HSRP VIP (Default GW) | DHCP Start IP |
|---:|---|---|---|
| 200 | Medical Records | 172.16.2.3 | 172.16.2.4 |
| 210 | Finance | 172.16.2.35 | 172.16.2.36 |
| 220 | Human Resources | 172.16.2.67 | 172.16.2.68 |

---

## 🏬 Floor 3 - DHCP Update

| VLAN | Department | HSRP VIP (Default GW) | DHCP Start IP |
|---:|---|---|---|
| 300 | Nurse DPT (F3) | 172.16.3.3 | 172.16.3.4 |
| 310 | ICU | 172.16.3.67 | 172.16.3.68 |
| 330 | Radiology | 172.16.3.131 | 172.16.3.132 |

---

## ✅ Verification

#### DHCP-SRV pool:

<img width="833" height="375" alt="DHCP-SRV-pool" src="https://github.com/user-attachments/assets/c230fa63-5aaa-4a3e-b100-de82139a86c7" />
