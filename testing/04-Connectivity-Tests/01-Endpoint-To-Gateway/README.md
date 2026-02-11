# 🧪 01 – Endpoint to Default Gateway Connectivity Tests

## 📌 Overview

This folder contains connectivity tests that verify end devices (PCs and and internal servers) can successfully reach their configured default gateway.

If an endpoint cannot reach its default gateway:

- Inter-VLAN routing will fail  
- Access to internal servers will fail  
- Internet connectivity will fail

---

## 🎯 Test Objective

For each floor and department:

- Verify correct default gateway configuration  
- Confirm successful ping to their default gateway (HSRP virtual IP Address)

---

## 🏢 Floors & Departments Covered

| Test File | Description |
|-----------|------------|
| [**`01-Test-Floor1-Endpoints-to-Default-Gateway.md`**](/testing/04-Connectivity-Tests/01-Endpoint-To-Gateway/01-Test-Floor1-Endpoints-to-Default-Gateway-Connectivity.md) | Verifies Floor 1 user devices can reach their VLAN gateway |
| [**`02-Test-Floor2-Endpoints-to-Default-Gateway.md`**](/testing/04-Connectivity-Tests/01-Endpoint-To-Gateway/02-Test-Floor2-Endpoints-to-Default-Gateway-Connectivity.md) | Verifies Floor 2 user devices can reach their VLAN gateway |
| [**`03-Test-Floor3-Endpoints-to-Default-Gateway.md`**](/testing/04-Connectivity-Tests/01-Endpoint-To-Gateway/03-Test-Floor3-Endpoint-to-Default-Gateway-Connectivity.md) | Verifies Floor 3 user devices can reach their VLAN gateway |
| [**`04-Test-IT-DPT-Endpoint-to-Default-Gateway.md`**](/testing/04-Connectivity-Tests/01-Endpoint-To-Gateway/04-Test-IT-DPT-Endpoint-to-Default-Gateway-Connectivity.md) | Verifies IT department devices can reach their gateway |
| [**`05-Test-Internal-Server-Endpoints-to-Default-Gateway.md`**](/testing/04-Connectivity-Tests/01-Endpoint-To-Gateway/05-Test-Internal-Server-Endpoints-to-Default-Gateway-Connectivity.md) | Verifies internal servers can reach their gateway |

---

## 🧪 Test Method

Each test file follows this structure:

1. Test Objective  
2. Source Device Information  
3. VLAN / Subnet Table  
4. Ping Command Used  
5. Ping Result  
6. Screenshot of the Results  

---

## 🔎 What This Validates

These tests confirm:

- VLAN configuration is correct  
- Access ports are properly assigned  
- Default Gateway are operational  
- Routing is functioning at the access layer  
- No local ACL is blocking traffic  

