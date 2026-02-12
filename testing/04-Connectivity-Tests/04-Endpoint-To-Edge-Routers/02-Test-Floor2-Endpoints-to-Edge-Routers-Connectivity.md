# 🧪 Test – Floor 2 Endpoints to Edge Routers Connectivity

## 📌 Purpose
This test verifies that Floor 2 endpoints can successfully reach the Edge Routers (HS-EDGE-R1 and HS-EDGE-R2).

> 💡 Successful replies confirm proper Layer 3 routing from Access → Distribution → Core → Edge.

## Reference Topology

<img width="784" height="639" alt="topology" src="https://github.com/user-attachments/assets/5e8733fb-7ee1-4ac0-b0b5-9877d5e5b8fc" />

---

## 🏢 Floor 2 Endpoints

| Device | VLAN | Subnet | IP Address | Connected Switch |
|--------|------|--------|------------|------------------|
| MRD-1 | 200 – Medical Records | 172.16.2.0/27 | 172.16.2.6 (DHCP) | F2-ASW1 |
| Fin-3 | 210 – Billing & Finance | 172.16.2.32/27 | 172.16.2.39 (DHCP) | F3-ASW3 |

---

## 🧪 Test 1 – MRD-1 → HS-EDGE-R1

```bash
ping 10.0.0.15      # HS-EDGE-R1 Loopback
ping 10.200.0.1     # HS-EDGE-R1 Port-Channel1
```

### MRD-1 to HS-EDGE-R1 ping was successful ✅

<img width="735" height="635" alt="MRD1-HS-EDGE-R1" src="https://github.com/user-attachments/assets/b019c815-f545-4894-83c6-7450a012b7ad" />

---

## 🧪 Test 1.5 – ED-1 → HS-EDGE-R1 and HS-EDGE-R2 Po10

```bash
ping 10.150.0.1     # HS-EDGE-R1 Port-Channel10
ping 10.150.0.2     # HS-EDGE-R2 Port-Channel10
```

### MRD-1 to HS-EDGE-R1 ping was successful ✅

<img width="695" height="593" alt="MRD1-Edge-Interconnection" src="https://github.com/user-attachments/assets/7540d4f6-37b6-4c98-9fa4-095f1258059f" />

---


## 🧪 Test 2 – Fin-3 → HS-EDGE-R2

```bash
ping 10.0.0.14      # HS-EDGE-R2 Loopback
ping 10.200.0.5     # HS-EDGE-R2 Port-Channel10
```

### Fin-3 to HS-EDGE-R2 ping was successful ✅

<img width="694" height="632" alt="Fin3-HS-EDGE-R2" src="https://github.com/user-attachments/assets/35fa0def-7a47-4ca2-aacc-455d8d9777b7" />

---

## 🎯 Result
-  Floor 2 endpoints successfully reached the Edge routers
