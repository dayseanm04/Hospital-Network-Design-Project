# 🧪 01 – Test Floor 1 Endpoints to Internal Servers

## 📌 Test Objective

Verify that Floor 1 endpoints can successfully reach internal servers located in the Server VLAN (VLAN 240 – 10.10.10.0/27).

This confirms:

- Inter-VLAN routing is operational
- OSPF is properly advertising VLAN subnets
- No ACL is blocking internal server access

## Reference Topology

<img width="784" height="639" alt="topology" src="https://github.com/user-attachments/assets/5e8733fb-7ee1-4ac0-b0b5-9877d5e5b8fc" />

---


## 🏢 Floor 1 Endpoints Tested

| Device | VLAN | Subnet | IP Address |
|--------|------|--------|------------|
| ED-1 | VLAN 101 | 172.16.1.0/26 | 172.16.1.4 (DHCP) |
| Nrs-1 | VLAN 120 | 172.16.1.96/26 | 172.16.1.102 (DHCP) |

---

## 🖥️ Internal Server

| Server | VLAN | Subnet | IP Address |
|--------|------|--------|------------|
| DHCP-SRV | VLAN 240 | 10.10.10.0/27 | 10.10.10.2 (Static) |

---

## 🧪 Test Command

From ED-1 ping DHCP-SRV:

```bash
ping 10.10.10.2
```

### ED-1 to DHCP-SRV ping was successful ✅

<img width="702" height="359" alt="ED1" src="https://github.com/user-attachments/assets/c3cbab56-8ccc-4255-b6f2-81bd896bcf80" />

---

## 🧪 Test Command

From F1-Nrs-1 ping DHCP-SRV:

```bash
ping 10.10.10.2
```

### F1-Nrs-1 to DHCP-SRV ping was successful ✅

<img width="700" height="367" alt="F1-Nrs-1" src="https://github.com/user-attachments/assets/00db142e-7275-47d3-9705-7c9e40daae52" />

