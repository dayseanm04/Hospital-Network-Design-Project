# Test Edge Router Redundancy and Failover

## Overview
This test verifies that the hospital network maintains internet connectivity when one edge router fails.

The hospital has two edge routers:
- HS-EDGE-R1
- HS-EDGE-R2

Traffic should automatically fail over to the remaining router if one goes down.

---

## Objective
- Verify redundancy between edge routers
- Confirm failover works during router failure
- Ensure continuous internet connectivity from hospital LAN

---

## Test Scenario

| Source | Destination | Purpose |
|--------|-------------|----------|
| ED-1 PC (172.16.1.5) | 70.70.70.10 | Test internet connectivity |

---
