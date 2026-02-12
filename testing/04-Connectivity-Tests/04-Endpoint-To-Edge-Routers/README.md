# 🌐 04 – Endpoint to Edge Routers Testing

## 📌 Overview

This folder contains validation tests that verify **Layer 3 connectivity from hospital endpoints to the Edge Routers (HS-EDGE-R1 and HS-EDGE-R2).**

These tests confirm:

- Access → Distribution → Core → Edge routing path
- Edge loopback reachability
- Port-Channels connectivity
- Redundant Edge router paths

> 💡 These tests validate that hospital VLANs can successfully reach the Edge layer before external/WAN testing.

---

## 🏢 Floors & Departments Covered


| Test File | Description |
|------------|------------|
| [**`01-Test-Floor1-Endpoints-to-Edge-Routers-Connectivity.md`**](/testing/04-Connectivity-Tests/04-Endpoint-To-Edge-Routers/01-Test-Floor1-Endpoints-to-Edge-Routers-Connectivity.md) | Verifies Floor 1 endpoints can reach HS-EDGE-R1 and HS-EDGE-R2 |
| [**`02-Test-Floor2-Endpoints-to-Edge-Routers-Connectivity.md`**](/testing/04-Connectivity-Tests/04-Endpoint-To-Edge-Routers/02-Test-Floor2-Endpoints-to-Edge-Routers-Connectivity.md) | Verifies Floor 2 endpoints can reach Edge routers |
| [**`03-Test-Floor3-Endpoint-to-Edge-Routers-Connectivity.md`**](/testing/04-Connectivity-Tests/04-Endpoint-To-Edge-Routers/03-Test-Floor3-Endpoint-to-Edge-Routers-Connectivity.md) | Verifies Floor 3 endpoints can reach Edge routers |
| [**`04-Test-IT-VLAN-to-Edge-Router-Connectivity.md`**](/testing/04-Connectivity-Tests/04-Endpoint-To-Edge-Routers/04-Test-IT-VLAN-to-Edge-Router-Connectivity.md) | Verifies IT VLAN reachability to Edge router infrastructure |

---

## 🧪 What Is Being Tested?

Each file validates:

- Edge Router Loopback Interfaces
- Port-Channel Interfaces
- Redundant routing paths
