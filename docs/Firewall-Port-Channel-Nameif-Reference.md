# 🔐 Firewall Port-Channel Nameif Reference

## 📌 Purpose

This document is the **reference for the Core firewalls Port-Channel interface naming (`nameif`) and security levels** 

## 🧱 Device Scope

| Device | Role |
|------|-----|
| HS-CORE-FW1 | Primary Core Firewall |
| HS-CORE-FW2 | Secondary Core Firewall |

---

## 🔌 HS-CORE-FW1 – Port-Channel Interfaces

| Interface | nameif | Description | Security Level | Connected To |
|---------|--------|-------------|----------------|--------------|
| Port-channel1 | OUTSIDE-ISP1 | To-HS-EDGE-R1 | 0 | ISP / Edge Router |
| Port-channel20 | INSIDE-A | To-DSW1 | 100 | Distribution Switch 1 |

---
