# Test Distribution Switches Redundancy and Failover

## Overview
This test verifies that the hospital network maintains connectivity when one distribution switch fails.

The hospital has two distribution switches:
- DSW1
- DSW2

Traffic from the access layer should be able to reach the edge routers through either distribution switch.

---

## Objective
- Verify redundancy at the distribution layer
- Confirm failover works during switch failure

---

##  Test Scenario

| Source | Destination | Purpose |
|--------|-------------|----------|
| MRD-1 PC (172.16.2.7)| 70.70.70.20 | Test internet connectivity |

---

## Test Steps

### Step 1 – Initial Connectivity Test

From MRD-1:

```cmd
ping 70.70.70.20
```

<img width="1065" height="409" alt="1" src="https://github.com/user-attachments/assets/225764bb-8a3f-4f01-baac-8732cd18a8f7" />

The ping was successful ✅

### Step 2 – Simulate Failure

Shut down DSW2

<img width="754" height="276" alt="11" src="https://github.com/user-attachments/assets/98235f48-9a64-4492-abd7-47ebd6da89cf" />

<img width="750" height="378" alt="12" src="https://github.com/user-attachments/assets/d452aa0d-075f-4536-9905-c11098d8cc58" />

### Reference Topology

<img width="620" height="495" alt="13" src="https://github.com/user-attachments/assets/cce01d2d-8ed3-42c1-af1e-66f46513c3fa" />

### Step 3 – Test Failover

From MRD-1 again ping ping 70.70.70.20

<img width="987" height="463" alt="14" src="https://github.com/user-attachments/assets/c61eed46-2943-4191-8b9e-58899bd54671" />

The ping was successful ✅
























