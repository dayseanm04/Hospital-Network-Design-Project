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
