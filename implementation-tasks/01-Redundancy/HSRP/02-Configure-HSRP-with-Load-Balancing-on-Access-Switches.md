# 🧩 03 – Configure HSRP with Load Balancing on Access Switches

In this task I will configures **HSRP (standby version 2)** on the **Access Layer switch pairs** to provide **default-gateway redundancy** while also **load-balancing** traffic by splitting which switch is **Active Router** per VLAN. 


> 📝 **Note:** I’m only using a few VLANs per floor to demonstrate HSRP.

## 🎯 HSRP Design (Load Balancing)

Instead of making one access switch the Active Router for every VLAN, I will balance the load for both switches, each floor will have an **Active/Standby Router** so both switches do work.

### 🏥 Active Gateway Plan (Per Floor)

| Floor | VLANs | Active Switch | Standby Switch |
|---|---|---|---|
| Floor 1 | 101 | F1-ASW1 | F1-ASW2 |
| Floor 1 | 110, 120 | F1-ASW2 | F1-ASW1 |
| Floor 2 | 200 | F2-ASW1 | F2-ASW2 |
| Floor 2 | 210, 220 | F2-ASW2 | F2-ASW1 |
| Floor 3 | 300 | F3-ASW1 | F3-ASW2 |
| Floor 3 | 310, 330 | F3-ASW2 | F3-ASW1 |

## Reference Network Diagram

<img width="824" height="486" alt="Reference" src="https://github.com/user-attachments/assets/26bfde52-214f-4332-9805-20dfa415f224" />

## 🧠 HSRP IPs and Priorities Used

**HSRP VIP = shared default gateway** for the VLAN  
**Priority:** `130 = Active`, `70 = Standby` (with `preempt`)

### 🏥 Floor 1 HSRP VIPs

| VLAN | Subnet | HSRP Group | HSRP Virtual IP (VIP) |
|---:|---|---:|---|
| 101 | 172.16.1.0/26 | 101 | 172.16.1.3 |
| 110 | 172.16.1.64/26 | 110 | 172.16.1.67 |
| 120 | 172.16.1.96/26 | 120 | 172.16.1.99 |

### 🏢 Floor 2 HSRP VIPs

| VLAN | Subnet | HSRP Group | HSRP Virtual IP (VIP) |
|---:|---|---:|---|
| 200 | 172.16.2.0/27 | 200 | 172.16.2.3 |
| 210 | 172.16.2.32/27 | 210 | 172.16.2.35 |
| 220 | 172.16.2.64/27 | 220 | 172.16.2.67 |


### 🏬 Floor 3 HSRP VIPs


| VLAN | Subnet | HSRP Group | HSRP Virtual IP (VIP) |
|---:|---|---:|---|
| 300 | 172.16.3.0/27 | 300 | 172.16.3.3 |
| 310 | 172.16.3.64/27 | 310 | 172.16.3.67 |
| 330 | 172.16.3.128/27 | 330 | 172.16.3.131 |

## ⚙️ Configuration (Use This on Any Floor)

### ✅ On the switch that should be **ACTIVE** for the VLAN

```bash
interface vlan <VLAN-ID>
 standby version 2
 standby <VLAN-ID> ip <HSRP-VIP>
 standby <VLAN-ID> priority 130
 standby <VLAN-ID> preempt
```

### ✅ On the switch that should be **STANDBY** for the VLAN

```bash
interface vlan <VLAN-ID>
 standby version 2
 standby <VLAN-ID> ip <HSRP-VIP>
 standby <VLAN-ID> priority 70
 standby <VLAN-ID> preempt
```

**Note 💡**: In this design, the HSRP group number = VLAN ID to keep things simple and consistent.


