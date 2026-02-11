# 🧪 02 – Endpoint-to-Endpoint Connectivity Tests

## 📌 Overview

This folder contains connectivity tests that verify communication between endpoints across the Hospital Network.

These tests validate:

- Same-VLAN communication (Layer 2 switching)
- Inter-VLAN communication (Layer 3 routing)
- Department-to-department communication

---

## 🏢 Floors & Departments Covered

| Test File | Description |
|-----------|------------|
| [**`01-Test-Floor1-Same-VLAN-Endpoint-to-Endpoint-Connectivity.md`**](/testing/04-Connectivity-Tests/02-Endpoint-To-Endpoint/01-Test-Floor1-Same-VLAN-Endpoint-to-Endpoint-Connectivity.md) | Verifies same-VLAN communication between Floor 1 endpoints |
| [**`02-Test-Floor2-Same-VLAN-Endpoint-to-Endpoint-Connectivity.md`**](/testing/04-Connectivity-Tests/02-Endpoint-To-Endpoint/02-Test-Floor2-Same-VLAN-Endpoint-to-Endpoint-Connectivity.md) | Verifies same-VLAN communication between Floor 2 endpoints |
| [**`03-Test-Floor3-Same-VLAN-Endpoint-to-Endpoint-Connectivity.md`**](/testing/04-Connectivity-Tests/02-Endpoint-To-Endpoint/03-Test-Floor3-Same-VLAN-Endpoint-to-Endpoint-Connectivity.md) | Verifies same-VLAN communication between Floor 3 endpoints |
| [**`04-Test-Inter-VLAN-Endpoint-to-Endpoint-Connectivity.md`**](/testing/04-Connectivity-Tests/02-Endpoint-To-Endpoint/04-Test-Inter-VLAN-Endpoint-to-Endpoint-Connectivity.md) | Verifies inter-VLAN routing between different user VLANs |
| [**`05-Test-IT-DPT-VLAN-to-Hospital-Endpoint-Connectivity.md`**](/testing/04-Connectivity-Tests/02-Endpoint-To-Endpoint/05-Test-IT-DPT-VLAN-to-Hospital-Endpoint-Connectivity.md) | Verifies IT department connectivity to other hospital endpoints |

---

## 🧪 Test Methodology

Each test file follows this validation structure:

1. Test Objective  
2.and Source Endpoint Information  
3. VLAN / Subnet Table  
4. Ping Command Used  
5. Ping Result
6. Screenshot of the Results

## 🔎 What These Tests Validate

These endpoint-to-endpoint tests confirm:

- Inter-VLAN routing is correctly configured
- OSPF is advertising VLAN subnets correctly
