# 🌐 Configure OSPF Backbone for Hospital Core and Edge

## 📌 Overview
This task., I will configure **OSPF Area 0 (Backbone)** across the **Hospital Edge Routers**, **Core Firewalls**, and **Distribution Switches**.  


## 🎯 Objective
- Enable **OSPF process 10** on all backbone devices
- Advertise their **loopback interfaces**
- Enable OSPF on **core, edge, and distribution backbone links**
- Verify OSPF neighbor relationships

## Topology For Reference

<img width="555" height="408" alt="topology1" src="https://github.com/user-attachments/assets/31a18433-4db7-45a7-ae0f-7fa3e2ac450f" />

---

## 🔧 Configuration Summary (What Is Enabled)

> The same OSPF process is used across all backbone devices.  
> I enabled OSPF using the **network** command, not interface-level commands.

### 🟦 On HS-EDGE-R1

In Global condif mode

```bash
router ospf 10
 network 10.0.0.15 0.0.0.0 area 0
 network 10.200.0.0 0.0.0.3 area 0
 network 10.150.0.0 0.0.0.3 area 0
```


### 🟦 On HS-EDGE-R2

```bash
router ospf 10
 network 10.0.0.14 0.0.0.0 area 0
 network 10.200.0.4 0.0.0.3 area 0
 network 10.150.0.0 0.0.0.3 area 0
```

| Network       | Purpose                  |
| ------------- | ------------------------ |
| 10.0.0.15/32  | HS-EDGE-R1 Loopback interface   |
| 10.0.0.15/32  | HS-EDGE-R2 Loopback interface  |
| 10.200.0.0/30 | HS-EDGE-R1 ↔ HS-CORE-FW1 |
| 10.200.0.4/30 | HS-EDGE-R2 ↔ HS-CORE-FW2 |
| 10.150.0.0/30 | HS-EDGE-R1 ↔ HS-EDGE-R2  |




