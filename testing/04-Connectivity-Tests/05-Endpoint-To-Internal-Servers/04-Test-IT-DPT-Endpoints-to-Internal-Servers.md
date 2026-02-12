# 🧪 04 – Test IT Department Endpoints to Internal Servers

## 📌 Test Objective

Verify that IT Department endpoints can successfully reach internal servers located in the Server VLAN (VLAN 240 – 10.10.10.0/27).

This confirms:

- Inter-VLAN routing is operational
- OSPF is properly advertising VLAN subnets
- No ACL is blocking internal server access

## Reference Topology

<img width="784" height="639" alt="topology" src="https://github.com/user-attachments/assets/5e8733fb-7ee1-4ac0-b0b5-9877d5e5b8fc" />

---


## 🏢 IT Department Endpoints Tested

| Device | VLAN | Subnet | IP Address | Switch |
|--------|------|--------|------------|--------|
| IT-PC1 | IT DPT VLAN | 10.50.50.0/26 | 10.50.50.2 (Static) | Service-ASW |
| IT-PC2 | IT DPT VLAN | 10.50.50.0/26 | 10.50.50.3 (Static) | Service-ASW |

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

### IT-PC1 to DHCP-SRV ping was successful ✅

<img width="694" height="348" alt="IT-PC1" src="https://github.com/user-attachments/assets/eb9e4f02-2e6d-4edd-a046-15024c5cc58f" />

---

## 🧪 Test Command

```bash
ping 10.10.10.2
```

### IT-PC2 to DHCP-SRV ping was successful ✅

<img width="696" height="366" alt="IT-PC2" src="https://github.com/user-attachments/assets/ea8d6491-7a10-4a9d-89c5-24ffcda63393" />

---

## 🔎 Validation Summary

- IT DPT VLAN can reach Server VLAN
- Inter-VLAN routing is functioning
- Internal services are reachable
