# 🔁 HSRP Gateway Redundancy Design for Hospital Network

## 📌 Overview
This document describes the **HSRP (Hot Standby Router Protocol) design** used at the **access layer** of the hospital network.

HSRP is implemented to provide:
- **Default gateway redundancy** for the Hospital Department VLANs
- **Load sharing** across access switches using a per-VLAN active/standby model
- **High availability** in the event of access switch failure

---

## 🧠 HSRP Design Principles

| Design Element | Description |
|---------------|------------|
| HSRP Mode | Active / Standby per VLAN |
| Gateway Redundancy | Yes (HSRP Virtual IP) |
| Load Sharing | Yes (different VLANs active on different switches) |
| HSRP VIP Addressing | **3rd usable IP address** of each subnet |
| Scope | Access Layer (Each Floor) |

---

## 🌐 HSRP Virtual IP Strategy

- Each VLAN uses an **HSRP Virtual IP (VIP)** as the default gateway
- The VIP is the **3rd usable IP address** in the subnet
- This provides consistency and avoids conflicts with SVI IP addresses

---

## 🧱 Floor 1 – HSRP Role Design

### VLANs
- **VLAN 101** – Emergency Department  
- **VLAN 110** – X-Ray / Imaging  
- **VLAN 120** – ED Nurse Offices  

### Active / Standby Assignment

| VLAN | Subnet | HSRP Virtual IP | Active Switch | Standby Switch |
|-----:|--------|----------------|---------------|----------------|
| 101 | 172.16.1.0/26 | 172.16.1.3 | F1-ASW1 | F1-ASW2 |
| 110 | 172.16.1.64/27 | 172.16.1.67 | F1-ASW2 | F1-ASW1 |
| 120 | 172.16.1.96/27 | 172.16.1.99 | F1-ASW2 | F1-ASW1 |

---

## 🧱 Floor 2 – HSRP Role Design

### VLANs
- **VLAN 200** – Medical Records  
- **VLAN 210** – Billing & Finance  
- **VLAN 220** – Human Resources  

### Active / Standby Assignment

| VLAN | Subnet | HSRP Virtual IP | Active Switch | Standby Switch |
|-----:|--------|----------------|---------------|----------------|
| 200 | 172.16.2.0/27 | 172.16.2.3 | F2-ASW1 | F2-ASW2 |
| 210 | 172.16.2.32/27 | 172.16.2.35 | F2-ASW2 | F2-ASW1 |
| 220 | 172.16.2.64/27 | 172.16.2.67 | F2-ASW2 | F2-ASW1 |

---


## 🧱 Floor 3 – HSRP Role Design

### VLANs
- **VLAN 300** – Nurse Offices  
- **VLAN 310** – ICU  
- **VLAN 330** – Radiology  

### Active / Standby Assignment

| VLAN | Subnet | HSRP Virtual IP | Active Switch | Standby Switch |
|-----:|--------|----------------|---------------|----------------|
| 300 | 172.16.3.0/26 | 172.16.3.3 | F3-ASW1 | F3-ASW2 |
| 310 | 172.16.3.64/27 | 172.16.3.67 | F3-ASW2 | F3-ASW1 |
| 330 | 172.16.3.128/27 | 172.16.3.131 | F3-ASW2 | F3-ASW1 |

---

## 📝 Design Notes
- Only **access-layer switches** participate in HSRP
