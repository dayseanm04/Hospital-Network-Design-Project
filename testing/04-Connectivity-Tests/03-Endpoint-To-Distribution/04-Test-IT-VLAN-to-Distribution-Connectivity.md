# Test – IT VLAN to Distribution Connectivity

## Purpose
This test verifies that the **IT Department VLAN (VLAN 240)** can successfully reach the **Distribution Layer (DSW1 / DSW2)** including loopback interfaces and port-channels.

## Successful replies confirm:
- Layer 3 routing from IT VLAN to Distribution layer
- Redundant paths to DSW1 and DSW2
-  Proper core/distribution reachability

## Reference Topology

<img width="1005" height="463" alt="Topology" src="https://github.com/user-attachments/assets/e5489238-85b4-4948-902c-18c321f365fb" />

---

# Source Endpoint – IT Department

| Device | VLAN | Subnet | IP Address | Address Type | Connected Switch |
|--------|------|--------|------------|--------------|------------------|
| IT-PC1 | 240 – IT DPT | 10.50.50.0/26 | 10.50.50.2 | Static | Service-ASW |

---

# Distribution Infrastructure Targets

| Target Device | Interface Type | IP Address |
|---------------|---------------|------------|
| DSW1 | Loopback | 10.0.0.10 |
| DSW1 | Port-Channel | 10.255.2.1 |
| DSW2 | Loopback | 10.0.0.11 |
| DSW2 | Port-Channel | 10.255.2.6 |

---

## Test 1 – IT-PC1 → DSW1

### Commands
```bash
ping 10.0.0.10      # DSW1 Loopback
ping 10.255.2.1     # DSW1 Port-Channel
```

### IT-PC1 to DSW1 ping was successful ✅

<img width="1047" height="751" alt="IT1-DSW1" src="https://github.com/user-attachments/assets/7aa7b50f-bb17-49eb-8f2a-0a40a99726b1" />

---

## Test 2 – IT-PC1 → DSW2

### Commands
```bash
ping 10.0.0.11      # DSW2 Loopback
ping 10.255.2.6     # DSW2 Port-Channel
```

### IT-PC1 to DSW2 ping was successful ✅

<img width="1051" height="741" alt="IT1-DSW2" src="https://github.com/user-attachments/assets/dabf33fa-f9e6-4303-aa16-03376b8c7a57" />

---

## Overall Test Summary

- IT VLAN successfully reached both Distribution switches
- Loopback interfaces are reachable
- Port-channel interfaces are reachable
