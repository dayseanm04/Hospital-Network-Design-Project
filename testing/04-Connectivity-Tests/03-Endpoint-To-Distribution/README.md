# 🏗️ 03 – Endpoint to Distribution Testing

## 📌 Overview

This folder contains validation tests that verify **Layer 3 connectivity from hospital endpoints to the Distribution Layer (DSW1 and DSW2).**

These tests confirm:

- Access → Distribution routing path
- Distribution switch loopback reachability
- Port-Channel interface connectivity
- Redundant uplink paths

> 💡 These tests validate internal routing up to the Distribution layer before Core and Edge Layer validation.

---

## 🏢 Floors & Departments Covered

| Test File | Description |
|------------|------------|
| [**`01-Test-Floor1-Endpoint-to-Distribution-Connectivity.md`**](/testing/04-Connectivity-Tests/03-Endpoint-To-Distribution/01-Test-Floor1-Endpoint-to-Distribution-Connectivity.md) | Verifies Floor 1 endpoints can reach DSW1 and DSW2 |
| [**`02-Test-Floor2-Endpoint-to-Distribution-Connectivity.md`**](/testing/04-Connectivity-Tests/03-Endpoint-To-Distribution/02-Test-Floor2-Endpoint-to-Distribution-Connectivity.md) | Verifies Floor 2 endpoints can reach Distribution switches |
| [**`03-Test-Floor3-Endpoint-to-Distribution-Connectivity.md`**](/testing/04-Connectivity-Tests/03-Endpoint-To-Distribution/03-Test-Floor3-Endpoint-to-Distribution-Connectivity.md) | Verifies Floor 3 endpoints can reach Distribution switches |
| [**`04-Test-IT-VLAN-to-Distribution-Connectivity.md`**](/testing/04-Connectivity-Tests/03-Endpoint-To-Distribution/04-Test-IT-VLAN-to-Distribution-Connectivity.md) | Verifies IT VLAN reachability to Distribution infrastructure |

---

## 🧪 What Is Being Tested?

Each test file validates:

- Distribution Switch Loopback Interfaces
- Port-Channel Interfaces (L3 EtherChannel)
- Redundant uplink paths
- OSPF route propagation
- Layer 3 reachability from access layer
