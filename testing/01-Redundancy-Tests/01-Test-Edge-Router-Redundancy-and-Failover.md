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

## Test Steps

### Step 1 – Initial Connectivity Test

From ED-1:

```cmd
ping 70.70.70.10
```

<img width="1043" height="383" alt="1" src="https://github.com/user-attachments/assets/43218a05-28dc-4673-9802-024e6666a606" />

The ping was successful ✅

### Step 2 – Simulate Failure

Shut down HS-EDGE-R1

<img width="747" height="242" alt="3" src="https://github.com/user-attachments/assets/ff7f875b-b0bc-4d6d-acab-98b6cbf28626" />

<img width="743" height="373" alt="4" src="https://github.com/user-attachments/assets/6284fe34-2b29-4f77-af4a-183aecabfbd0" />

### Reference Topology

<img width="603" height="492" alt="5" src="https://github.com/user-attachments/assets/076ad576-2a04-4a2d-a9c8-777eea21f12b" />





