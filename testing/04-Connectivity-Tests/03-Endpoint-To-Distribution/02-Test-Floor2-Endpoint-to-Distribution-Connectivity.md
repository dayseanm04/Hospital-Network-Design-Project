# Test – Floor 2 Endpoint to Distribution Connectivity

## Purpose

This test verifies that Floor 2 endpoints can reach Distribution Switch infrastructure (DSW1 / DSW2 loopbacks and Port-Channels).

> Successful replies confirm proper Layer 3 routing from Access → Distribution layer.

## Reference Topology

<img width="1005" height="463" alt="Topology" src="https://github.com/user-attachments/assets/e5489238-85b4-4948-902c-18c321f365fb" />

---


## Floor 2 Endpoints

| Device | VLAN | Subnet | IP Address | Connected Switch |
|--------|------|--------|------------|------------------|
| MRD-1 | 200 – Medical Records | 172.16.2.0/27 | 172.16.2.4 (DHCP) | F2-ASW1 |
| MRD-3 | 200 – Medical Records | 172.16.2.0/27 | 172.16.2.6 (DHCP) | F2-ASW2 |


Note: there are multple PCs in on Floor 2 and I some of them for demonstration. 

---

## Test 1 – MRD-1 → DSW1


```bash
ping 10.0.0.10      # DSW1 Loopback
ping 10.10.0.9      # DSW1 Port-Channel3
```

## MDR-1 to DSW1 ping was successful ✅

<img width="1064" height="750" alt="MRD1-DSW1" src="https://github.com/user-attachments/assets/07674933-0829-4fc3-a442-076602c70974" />

---

## Test 2 – MRD-3 → DSW2

```bash
ping 10.0.0.11      # DSW2 Loopback
ping 10.20.0.13     # DSW2 Port-Channel4
```

## MRD-3 to DSW2 ping was successful ✅

<img width="1112" height="781" alt="MRD-3-DSW2" src="https://github.com/user-attachments/assets/df404fb5-317f-4481-953b-a916082d5c12" />

---

## Result

Floor 2 endpoints can reach both Distribution switches
