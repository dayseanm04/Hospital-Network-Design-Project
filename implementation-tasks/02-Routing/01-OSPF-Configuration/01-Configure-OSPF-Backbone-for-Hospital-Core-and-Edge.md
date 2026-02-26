# Configure OSPF Backbone for Hospital Core and Edge

## Overview
This task., I will configure **OSPF Area 0 (Backbone)** across the **Hospital Edge Routers**, **Core Firewalls**, and **Distribution Switches**.  


## Objective
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

### 🟧 On HS-CORE-FW1

```bash
router ospf 10
 router-id 10.0.0.20
 network 10.200.0.0 255.255.255.252 area 0
 network 10.255.0.0 255.255.255.252 area 0
```

### 🟧 On HS-CORE-FW2

```bash
router ospf 10
 router-id 10.0.0.21
 network 10.200.0.4 255.255.255.252 area 0
 network 10.255.0.4 255.255.255.252 area 0
```

| Network       | Purpose             |
| ------------- | ------------------- |
| 10.200.0.0/30 | HS-CORE-FW1 ↔ HS-EDGE-R1|
| 10.255.0.0/30 | HS-CORE-FW1 ↔ DSW1 |
| 10.200.0.4/30 | HS-CORE-FW2 ↔ HS-EDGE-R2  |
| 10.255.0.4/30 | HS-CORE-FW2 ↔ DSW2 |

### 🟩 On DSW1

```bash
router ospf 10
 network 10.0.0.10 0.0.0.0 area 0
 network 10.255.0.0 0.0.0.3 area 0
 network 10.255.1.0 0.0.0.3 area 0
```

### 🟩 On DSW2

```bash
router ospf 10
 network 10.0.0.11 0.0.0.0 area 0
 network 10.255.0.4 0.0.0.3 area 0
 network 10.255.1.0 0.0.0.3 area 0
```

## Topology For Reference

<img width="555" height="408" alt="topology1" src="https://github.com/user-attachments/assets/31a18433-4db7-45a7-ae0f-7fa3e2ac450f" />

---

## Verification

### show ip ospf neighbor on HS-EDGE-R1

<img width="825" height="138" alt="EDGE-1" src="https://github.com/user-attachments/assets/b451e2a8-b3c1-46ba-ba27-4bdb227745b1" />

### show ip ospf neighbor on HS-EDGE-R2

<img width="835" height="136" alt="EDGE-2" src="https://github.com/user-attachments/assets/92640222-d69f-45db-b189-591ba334a530" />

### show ip ospf neighbor on DSW1

<img width="837" height="243" alt="DSW1" src="https://github.com/user-attachments/assets/64ea95bd-ac4a-4052-81aa-329a29695dcf" />

### show ip ospf neighbor on DSW2

<img width="849" height="261" alt="DSW2" src="https://github.com/user-attachments/assets/fc7d4cda-191e-4295-8199-ebf362ae4a2f" />

Note: the adjacencies toward Core Firewalls are stuck in EXSTART state.

---

### [✅ Click here for Tropbleshoot OSPF Adjacency Stuck in EXSTART State](/troubleshooting/02-Routing/02-Troubleshoot-OSPF-Adjacency-Stuck-in-EXSTART.md)
