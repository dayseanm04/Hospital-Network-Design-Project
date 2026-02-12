# 🧪 03 – Test Floor 3 Endpoints to Internal Servers

## 📌 Test Objective

Verify that Floor 3 endpoints can successfully reach internal servers located in the Server VLAN (VLAN 240 – 10.10.10.0/27).

This confirms:

- Inter-VLAN routing is operational
- OSPF is properly advertising VLAN subnets
- No ACL is blocking internal server access

## Reference Topology

<img width="784" height="639" alt="topology" src="https://github.com/user-attachments/assets/5e8733fb-7ee1-4ac0-b0b5-9877d5e5b8fc" />

---

## 🏢 Floor 3 Endpoints Tested

| Device | VLAN | Subnet | IP Address |
|--------|------|--------|------------|
| ICU-1 | VLAN 310 | 172.16.3.64/26 | 172.16.3.69 (DHCP) |
| Rad-3 | VLAN 330 | 172.16.3.128/26 | 172.16.3.133 (DHCP) |

---

## 🖥️ Internal Server

| Server | VLAN | Subnet | IP Address |
|--------|------|--------|------------|
| DHCP-SRV | VLAN 240 | 10.10.10.0/27 | 10.10.10.2 (Static) |

---

## 🧪 Test Command

```bash
ping 10.10.10.2
```

### ICU-1 to DHCP-SRV ping was successful ✅

<img width="697" height="367" alt="ICU1" src="https://github.com/user-attachments/assets/d48ebd51-9774-4c67-a306-607b24a81e57" />

---

## 🧪 Test Command

```bash
ping 10.10.10.2
```

### Rad-3 to DHCP-SRV ping was successful ✅

<img width="703" height="358" alt="Rad3" src="https://github.com/user-attachments/assets/b044f34d-c7e3-4a29-9cb9-4ef86311aace" />

---

## 🔎 Validation Summary

- Floor 3 VLANs can reach Server VLAN
- Inter-VLAN routing is functioning
- Internal services are reachable
