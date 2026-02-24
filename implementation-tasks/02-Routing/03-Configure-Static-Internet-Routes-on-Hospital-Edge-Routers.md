# Configure Static Internet Routes on Hospital Edge Routers.md

## Overview
This task, I will configure static routes on the hospital edge routers so internal traffic can reach the simulated internet network.

The internet network used in this project is:

200.10.0.0/24

---

## Objective
- Configure internet-bound static routes
- Ensure hospital LAN traffic exits toward ISP1
- Demonstrate internet reachability using static routing

---

# Configuration

## On HS-EDGE-R1

```plaintext
ip route 200.10.0.0 255.255.255.0 69.45.12.1
```

