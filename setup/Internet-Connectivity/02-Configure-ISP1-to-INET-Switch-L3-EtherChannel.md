# 🔗 Configure ISP1 to INET Switch L3 EtherChannel

## 📌 Overview
In this task, I will configure a **Layer 3 EtherChannel (Port-Channel 1)** between the **ISP1-R1** and the **INET switch (INET-SW)**.  
This bundles **two physical uplinks** into one logical routed interface to improve:

- ✅ **Redundancy** (link failover)
- ✅ **Bandwidth** (links combined)
- ✅ **Stability** (single logical L3 interface)

## 🎯 Goal
Create an **L3 Port-Channel** between:
- **ISP1 ↔ INET-SW**
- Routed subnet: **10.30.30.0/30**

## Topology For Reference

<img width="745" height="301" alt="reference-topology" src="https://github.com/user-attachments/assets/73b21ac5-75e3-407e-8ebe-3b05a0f6bf89" />

---

## 🔌 Physical Connections

| Device | Interface | Connected To | Interface |
|------|----------|-------------|-----------|
| ISP1 | G1/1/3 | INET-SW | G1/1/1 |
| ISP1 | G1/1/4 | INET-SW | G1/1/2 |

---


## 🧠 IP Addressing Plan (Port-Channel 1)

| Device | Interface | IP Address | Subnet Mask | Network |
|-------|----------|------------|------------|---------|
| ISP1 | Port-channel1 | 10.30.30.1 | 255.255.255.252 | 10.30.30.0/30 |
| INET-SW | Port-channel1 | 10.30.30.2 | 255.255.255.252 | 10.30.30.0/30 |

---




















