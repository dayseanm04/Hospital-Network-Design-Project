# 🗄️ 03 – Configure INET Server VLAN and SVI

## 📌 Overview

In this task, I will configure a **dedicated VLAN for INET servers** on the **INET switch (INET-SW)**.  
This includes creating the VLAN and configuring an **SVI (Switched Virtual Interface)** to act as the **default gateway** for the INET server subnet.

## 🎯 Objectives
- Create a dedicated VLAN for INET servers
- Assign server interfaces to the VLAN
- Configure an SVI to provide Layer 3 connectivity
- Enable communication between INET servers and upstream devices


## Topology For Reference

<img width="745" height="301" alt="reference-topology" src="https://github.com/user-attachments/assets/73b21ac5-75e3-407e-8ebe-3b05a0f6bf89" />

---

## 🧠 INET Server Network Details

| Item | Value |
|-----|------|
| VLAN ID | 50 |
| VLAN Name | INET-SRVs |
| Server Subnet | 10.20.20.0/24 |
| Default Gateway | 10.20.20.1 |
| Device | INET-SW |

---

## 🛠️ Step 1 — Create INET Server VLAN

#### 🔷 On INET-SW, enter global configuration mode and create the VLAN:

```bash
vlan 50
 name INET-SRVs
```

## 🔌 Step 2 — Assign Server Ports to VLAN 50

#### 🔷 Assign server interfaces to the INET server VLAN.

```bash
interface range g1/0/2-24
 switchport mode access
 switchport access vlan 50
```

## 🌐 Step 3 — Configure INET Server VLAN SVI

#### 🔷 Configure the SVI for VLAN 50.

```bash
interface vlan 50
 ip address 10.20.20.1 255.255.255.0
 no shutdown
```

## ✅ Step 4 - Verification

```bash
show vlan brief
```

<img width="946" height="209" alt="INET-SRVs-VLANs" src="https://github.com/user-attachments/assets/02aac87a-4e72-4550-9beb-3e4dd082ff51" />

```bash
show ip int brief | include Vlan
```

<img width="827" height="83" alt="INET-SRV-VLAN-SVI" src="https://github.com/user-attachments/assets/32a17f03-f267-431e-92ad-2d39ca7c1a71" />
