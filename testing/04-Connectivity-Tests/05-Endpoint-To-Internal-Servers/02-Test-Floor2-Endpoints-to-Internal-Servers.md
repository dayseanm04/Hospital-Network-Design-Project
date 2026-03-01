# 02 – Test Floor 2 Endpoints to Internal Servers

## Test Objective

Verify that Floor 2 endpoints can successfully reach internal servers located in the Server VLAN (VLAN 240 – 10.10.10.0/27).

This confirms:

- Inter-VLAN routing is operational
- OSPF is properly advertising VLAN subnets
- No ACL is blocking internal server access

## Reference Topology

<img width="784" height="639" alt="topology" src="https://github.com/user-attachments/assets/5e8733fb-7ee1-4ac0-b0b5-9877d5e5b8fc" />

---

## Floor 2 Endpoints Tested

| Device | VLAN | Subnet | IP Address |
|--------|------|--------|------------|
| MRD-1 | VLAN 200 | 172.16.2.0/27 | 172.16.2.6 (DHCP) |
| Fin-3 | VLAN 210 | 172.16.2.32/27 | 172.16.2.39 (DHCP) |

---

## Internal Server

| Server | VLAN | Subnet | IP Address |
|--------|------|--------|------------|
| DHCP-SRV | VLAN 240 | 10.10.10.0/27 | 10.10.10.2 (Static) |

---

## Test Command

```bash
ping 10.10.10.2
```

### MRD-1 to DHCP-SRV ping was successful ✅

<img width="695" height="352" alt="MRD1" src="https://github.com/user-attachments/assets/8cd67fbe-2f8a-4548-a160-0d6600dfab11" />

---

## Test Command

```bash
ping 10.10.10.2
```

### F1-Nrs-1 to DHCP-SRV ping was successful ✅

<img width="696" height="359" alt="Fin3" src="https://github.com/user-attachments/assets/6b9fa513-5adb-4e4c-9a50-df39c4993767" />

---

## Validation Summary

- Floor 2 VLANs can reach Server VLAN
- Inter-VLAN routing is functioning
- Internal services are reachable
