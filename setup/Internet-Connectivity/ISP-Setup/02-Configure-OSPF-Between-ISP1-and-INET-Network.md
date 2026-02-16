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


## Topology For Reference

<img width="878" height="342" alt="topology" src="https://github.com/user-attachments/assets/a853c95c-6652-4a73-8038-789339e1b966" />

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

#### 🔷 In gGlobal config mode:

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

#### 🔷 This advertises:

- The ISP1 ↔ INET network
- The INET Servers subnet
- The INET-SW loopback (/32)


## ✅ Step 2 - Configure Default Route on ISP1

#### 🔷 On ISP1, configure a default route (floadint static route) pointing toward the hospital Edge Routers:

```bash
ip route 0.0.0.0 0.0.0.0 69.45.12.2
ip route 0.0.0.0 0.0.0.0 100.45.12.2 50
```

## ✅ Step 3 - Configure OSPF on ISP1-R1

#### 🔷 In Global config mode:

### 🧩 Configure Loopback0

```bash
interface loopback 0
 ip address 10.10.10.10 255.255.255.255
 exit
```

### 🧩  Enable OSPF Process 10 (Area 0)

```bash
router ospf 10
 network 10.30.30.0 0.0.0.255 area 0
 network 10.10.10.10 0.0.0.0 area 0
```

## ✅ Step 4 - Advertise Default Route into OSPF

```bash
 default-information originate
```

## ✅ Verification

#### 🔷 On ISP1-R1 show ip protocols

<img width="676" height="365" alt="ISP1-R1" src="https://github.com/user-attachments/assets/a05dd731-0218-44a8-8680-2e4f1ef1c944" />


#### 🔷 On INET-SW show ip protocols

<img width="825" height="346" alt="INET1-ospf" src="https://github.com/user-attachments/assets/eb866c33-624a-453f-9bba-e625d16a2738" />
