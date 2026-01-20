# 🧭 Configure OSPF Between ISP1 and INET Network

## 📌 Overview

In this task, I will configure **OSPF process 10 (Area 0)** between the **ISP1-R1** and the **INET network** so routing information can be exchanged dynamically.

I will also:
- Create **Loopback0** interfaces on both devices (for stable router IDs/testing)
- Enable **OSPF Area 0** on the INET uplink and INET server subnet
- Configure a **default route on ISP1**
- Advertise the default route into OSPF using **default-information originate**

---

## 🎯 Goals
- ✅ Enable OSPF between ISP1-R1 and INET-SW
- ✅ Advertise INET server subnet into OSPF
- ✅ Advertise default route
- ✅ Configure loopbacks

---

## Topology For Reference

<img width="745" height="301" alt="reference-topology" src="https://github.com/user-attachments/assets/efe4388b-2f59-4b9e-851a-c135db1689ad" />

---

## 🧠 Addressing / Networks Used

| Network  | Purpose |
|---|---|
| 10.30.30.0/30 | ISP1 ↔ INET-SW routed EtherChannel uplink |
| 10.20.20.0/24 | INET Servers subnet (VLAN 50 SVI on INET-SW) |
| 10.10.10.1/32 | INET-SW Loopback0 |
| 10.10.10.10/32 | ISP1 Loopback0 |
| 0.0.0.0/0 | Advertised default route into OSPF |

---

# 🛠 Step-by-Step Configuration


## ✅ Step 1 - Configure OSPF on INET-SW

### 🧩 Create Loopback0

```bash
interface loopback 0
 ip address 10.10.10.1 255.255.255.255
 exit
```

## 🧩 1.2 Enable OSPF Process 10 (Area 0)

```bash
router ospf 10
 network 10.30.30.0 0.0.0.255 area 0
 network 10.20.20.0 0.0.0.255 area 0
 network 10.10.10.1 0.0.0.0 area 0
```


































