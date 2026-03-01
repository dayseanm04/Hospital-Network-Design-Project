# Test – Floor 1 Same VLAN Endpoint-to-Endpoint Connectivity

## Purpose

This test verifies **intra-VLAN connectivity** between endpoints in the **same VLAN** on Floor 1.

> These tests confirm that devices within the same broadcast domain can communicate properly across access switches (F1-ASW1 and F1-ASW2).

## Reference Topology

<img width="1005" height="463" alt="Topology" src="https://github.com/user-attachments/assets/e5489238-85b4-4948-902c-18c321f365fb" />

---

# Floor 1 – Intra-VLAN Connectivity Tests


## Test 1 – Emergency Department (VLAN 101)

### IP Addressing

| Device | IP Address | Address Type | Subnet Mask | Default Gateway |
|---------|------------|--------------|-------------|-----------------|
| ED-1 | 172.16.1.4 | DHCP | 255.255.255.192 | 172.16.1.3 |
| ED-PRNT | 172.16.1.31 | Static | 255.255.255.192 | 172.16.1.3 |


### Devices Tested
- **ED-1** (PC – DHCP)
- **ED-PRNT** (Printer – Static)

### VLAN Information
- VLAN: **101 – Emergency DPT**
- Subnet: **172.16.1.0/26**
- Default Gateway: **172.16.1.3**
- ED-1 connected to **F1-ASW1**
- ED-PRNT connected to **F1-ASW2**

### Test Command

```bash
ping 172.16.1.31
```

### ED1 ping was successful ✅

<img width="701" height="397" alt="ED1" src="https://github.com/user-attachments/assets/ae225111-5c7d-4a15-91c6-a4f1741a8692" />

---

# Test 2 – X-Ray Department (VLAN 110)

| Device   | IP Address  | Address Type | Subnet Mask     | Default Gateway |
| -------- | ----------- | ------------ | --------------- | --------------- |
| X-R-1    | 172.16.1.68 | DHCP         | 255.255.255.224 | 172.16.1.67     |
| X-R-PRNT | 172.16.1.80 | Static       | 255.255.255.224 | 172.16.1.67     |

---

### Devices Tested

- **X-R-1** (PC – DHCP)
- **X-R-PRNT** (Printer – Static)

### VLAN Information

- VLAN: 110 – X-Ray DPT
- Subnet: 172.16.1.64/27
- Default Gateway: 172.16.1.67
- X-R-1 connected to F1-ASW1
- X-R-PRNT connected to F1-ASW2

### XR-1 ping was successful ✅

<img width="706" height="405" alt="X-R-1" src="https://github.com/user-attachments/assets/d09fc445-5e55-48b5-a77d-9f85594b042a" />

---

# Test 3 – F1 ED Nurses Department (VLAN 120)

| Device   | IP Address   | Address Type | Subnet Mask     | Default Gateway |
| -------- | ------------ | ------------ | --------------- | --------------- |
| Nrs-1    | 172.16.1.101 | DHCP         | 255.255.255.224 | 172.16.1.99     |
| Nrs-PRNT | 172.16.1.120 | Static       | 255.255.255.224 | 172.16.1.99     |

---

### Devices Tested

- **Nrs-1** (PC – DHCP)
- **Nrs-PRNT** (Printer – Static)

### VLAN Information

- VLAN: 120 – Floor 1 Emergency DPT Nurses
- Subnet: 172.16.1.96/27
- Default Gateway: 172.16.1.99
- Both devices connected to F1-ASW2

### Nrs-1 ping was successful ✅

<img width="700" height="400" alt="Nrs-1" src="https://github.com/user-attachments/assets/923c9257-52e9-4933-88a8-20f87e7b1989" />

---

### Overall Test Summary

All Floor 1 endpoints successfully communicated within their respective VLANs
