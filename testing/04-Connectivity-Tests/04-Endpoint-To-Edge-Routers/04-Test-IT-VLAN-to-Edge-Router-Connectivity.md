# Test – IT VLAN to Edge Router Connectivity

## Purpose
This test verifies that the **IT Department VLAN (VLAN 240)** can successfully reach the **Edge Routers (HS-EDGE-R1 and HS-EDGE-R2)**.

### Successful replies confirm:
- Layer 3 routing from IT VLAN to Edge layer
- Redundant Edge router paths are operational
- Core-to-Edge connectivity is functioning correctly

## Reference Topology

<img width="784" height="639" alt="topology" src="https://github.com/user-attachments/assets/5e8733fb-7ee1-4ac0-b0b5-9877d5e5b8fc" />

---


# Source Endpoint – IT Department

| Device | VLAN | Subnet | IP Address | Address Type | Connected Switch |
|--------|------|--------|------------|--------------|------------------|
| IT-PC1 | 240 – IT DPT | 10.50.50.0/26 | 10.50.50.2 | Static | Service-ASW |

---

# Edge Router

| Target Device | Interface Type | IP Address |
|---------------|---------------|------------|
| HS-EDGE-R1 | Loopback | 10.0.0.15 |
| HS-EDGE-R1 | Port-Channel10 | 10.200.0.1 |
| HS-EDGE-R2 | Loopback | 10.0.0.14 |
| HS-EDGE-R2 | Port-Channel10 | 10.200.0.5 |

---

## Test 1 – IT-PC1 → HS-EDGE-R1

### Commands
```bash
ping 10.0.0.15      # HS-EDGE-R1 Loopback
ping 10.200.0.1     # HS-EDGE-R1 Port-Channel1
ping 10.150.0.1     # HS-EDGE-R1 Port-Channel10
ping 10.150.0.2     # HS-EDGE-R2 Port-Channel10
```

### IT-PC1 to HS-EDGE-R1 ping was successful ✅

<img width="701" height="527" alt="IT-PC1-HS-EDGE-R1" src="https://github.com/user-attachments/assets/686bc86f-136f-46a9-aa97-602efece7463" />

---

## Test 1.5 – IT-PC1 → HS-EDGE-R1 and HS-EDGE-R2 Po10

```bash

ping 10.150.0.1     # HS-EDGE-R1 Port-Channel10
ping 10.150.0.2     # HS-EDGE-R2 Port-Channel10
```

### IT-PC1 to HS-EDGE-R1 and HS-EDGE-R2 Po10 ping was successful ✅

<img width="701" height="619" alt="IT-PC1-Edge-Interconnection" src="https://github.com/user-attachments/assets/f9507f0f-6801-408d-86a9-8063a8f9f96b" />

---

## Test 2 – IT-PC1 → HS-EDGE-R2

### Commands
```bash
ping 10.0.0.14      # HS-EDGE-R2 Loopback
ping 10.200.0.5     # HS-EDGE-R2 Port-Channel10
```

### IT-PC1 to HS-EDGE-R2 ping was successful ✅

<img width="692" height="621" alt="IT-PC1-HS-EDGE-R2" src="https://github.com/user-attachments/assets/b1650ce8-3712-48fb-905b-0e1ca271f3cd" />

---

## Overall Test Summary

- IT DPT VLAN successfully reached both Edge routers
- Loopback interfaces reachable (routing validation)
