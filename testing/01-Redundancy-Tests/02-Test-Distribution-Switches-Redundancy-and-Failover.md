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




