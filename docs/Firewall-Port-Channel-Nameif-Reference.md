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
| Port-channel1 | OUTSIDE-ISP1 | To-HS-EDGE-R1 | 0 | Edge Router 1 |
| Port-channel20 | INSIDE-A | To-DSW1 | 100 | Distribution Switch 1 |

---

## 🔌 HS-CORE-FW2 – Port-Channel Interfaces

| Interface | nameif | Description | Security Level | Connected To |
|---------|--------|-------------|----------------|--------------|
| Port-channel1 | OUTSIDE-ISP2 | To-HS-EDGE-R2 | 0 | Edge Router 2 |
| Port-channel20 | INSIDE-B | To-DSW2 | 100 | Distribution Switch 2 |

---

## 🧭 Security Level Reference

| Security Level | Zone Type | Typical Usage |
|---------------|----------|---------------|
| 0 | Outside | ISP / Untrusted Networks |
| 100 | Inside | Internal / Trusted Networks |

---

## ⚠️ Important Notes

- Firewall interfaces **must have a `nameif` configured** to fully participate in:
  - Routing protocols (OSPF)
  - ACLs and security policies
- Missing `nameif` configuration can cause **OSPF adjacencies to stall** (e.g., EXSTART state). [I ran into this problem earlier] See bellow:

### [✅ Click here for Tropbleshoot OSPF Adjacency Stuck in EXSTART State](/troubleshooting/02-Routing/02-Troubleshoot-OSPF-Adjacency-Stuck-in-EXSTART.md)
