# Configure Static Internet Routes on Hospital Edge Routers.md

## Reference topology

<img width="672" height="393" alt="topology" src="https://github.com/user-attachments/assets/e8cb1b2b-8591-4c1a-bb90-9f74d1080d54" />


## Overview
This task, I will configure static routes on the hospital edge routers so internal traffic can reach the simulated internet network.

The internet network used in this project is: **`200.10.0.0/24`**


## Objective
- Configure internet-bound static routes
- Ensure hospital LAN traffic exits toward ISP1
- Demonstrate internet reachability using static routing

# Configuration

## On HS-EDGE-R1

```plaintext
ip route 200.10.0.0 255.255.255.0 69.45.12.1
```

## On HS-EDGE-R2

```plaintext
ip route 200.10.0.0 255.255.255.0 100.45.12.1
```

### Verification


#### On HS-EDGE-R1 show ip route static

<img width="627" height="134" alt="E1" src="https://github.com/user-attachments/assets/8ab98eab-dfa4-466c-8f0e-ebc15ec6ab28" />




