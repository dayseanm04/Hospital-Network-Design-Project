# 🧪 Test – Internal Server Endpoints to Default Gateway Connectivity

## 📌 Purpose
This test verifies that **Hospital internal servers** can successfully reach their **default gateway** within the Servers VLAN.

> 💡 These servers provide critical network services.

---

## 🖥️ Internal Servers VLAN Overview

| Server Name | Service Role | VLAN ID | Subnet | Default Gateway | Connected Switch |
|------------|-------------|--------|--------|----------------|------------------|
| DHCP-SRV | DHCP Server | VLAN 700 | 10.10.10.0/27 | 10.10.10.1 | Service-ASW |
| NTP-SRV | NTP Server | VLAN 700 | 10.10.10.0/27 | 10.10.10.1 | Service-ASW |
| SYSLOG-SRV | Syslog Server | VLAN 700 | 10.10.10.0/27 | 10.10.10.1 | Service-ASW |

---
