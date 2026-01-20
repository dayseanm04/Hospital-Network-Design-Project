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
