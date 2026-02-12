# 🖥️ 05 – Endpoint to Internal Servers Connectivity Testing

## 📌 Overview

This folder contains validation tests that verify **Layer 3 connectivity from hospital endpoints to internal servers.**

These tests confirm:

- Inter-VLAN routing to the Services VLAN
- Reachability to DHCP, NTP, and Syslog servers
- Internal service availability across all floors
- IT VLAN access to infrastructure services

---

## 🏢 Floors & Departments Covered

| Test File | Description |
|------------|------------|
| [**`01-Test-Floor1-Endpoints-to-Internal-Servers.md`**](/testing/04-Connectivity-Tests/05-Endpoint-To-Internal-Servers/01-Test-Floor1-Endpoints-to-Internal-Servers.md) | Verifies Floor 1 endpoints can reach internal servers |
| [**`02-Test-Floor2-Endpoints-to-Internal-Servers.md`**](/testing/04-Connectivity-Tests/05-Endpoint-To-Internal-Servers/02-Test-Floor2-Endpoints-to-Internal-Servers.md) | Verifies Floor 2 endpoints can reach internal servers |
| [**`03-Test-Floor3-Endpoints-to-Internal-Servers.md`**](/testing/04-Connectivity-Tests/05-Endpoint-To-Internal-Servers/03-Test-Floor3-Endpoints-to-Internal-Servers.md) | Verifies Floor 3 endpoints can reach internal servers |
| [**`04-Test-IT-DPT-Endpoints-to-Internal-Servers.`md**](/testing/04-Connectivity-Tests/05-Endpoint-To-Internal-Servers/04-Test-IT-DPT-Endpoints-to-Internal-Servers.md) | Verifies IT VLAN endpoints can reach internal servers |

---
