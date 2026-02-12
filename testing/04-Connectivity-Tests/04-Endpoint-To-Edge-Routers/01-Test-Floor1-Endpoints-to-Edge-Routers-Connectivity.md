# 🧪 Test – Floor 1 Endpoints to Edge Routers Connectivity

## 📌 Purpose
This test verifies that Floor 1 endpoints can successfully reach the Edge Routers (HS-EDGE-R1 and HS-EDGE-R2).

> 💡 Successful replies confirm proper Layer 3 routing from Access → Distribution → Core → Edge.

## Reference Topology

<img width="784" height="639" alt="topology" src="https://github.com/user-attachments/assets/5e8733fb-7ee1-4ac0-b0b5-9877d5e5b8fc" />


---

## 🏢 Floor 1 Endpoints

| Device | VLAN | Subnet | IP Address | Connected Switch |
|--------|------|--------|------------|------------------|
| ED-1 | 101 – Emergency | 172.16.1.0/26 | 172.16.1.4 (DHCP) | F1-ASW1 |
| Nrs-1 | 120 – F1 Nurses | 172.16.1.96/26 | 172.16.1.102 (DHCP) | F1-ASW2 |

---

## 🧪 Test 1 – ED-1 → HS-EDGE-R1

```bash
ping 10.0.0.15      # HS-EDGE-R1 Loopback
ping 10.200.0.1     # HS-EDGE-R1 Port-Channel1
ping 10.150.0.1     # HS-EDGE-R1 Port-Channel10
ping 10.150.0.1     # HS-EDGE-R2 Port-Channel10

```

### ED-1 to HS-EDGE-R1 ping was successful ✅

<img width="701" height="628" alt="ED1-HS-EDGE-R1" src="https://github.com/user-attachments/assets/8fd231a6-3f13-4fd0-a21f-886235c2789a" />

---


## 🧪 Test 2 – Nrs-1 → HS-EDGE-R2

```bash
ping 10.0.0.14      # HS-EDGE-R2 Loopback
ping 10.200.0.5     # HS-EDGE-R2 Port-Channel10
```

### F1-Nrs-1 to HS-EDGE-R2 ping was successful ✅

<img width="688" height="619" alt="F1-Nrs-1-HS-EDGE-R2" src="https://github.com/user-attachments/assets/f6477193-0c01-4e70-9bf8-6287594b4dad" />

---

## 🎯 Result
-  Floor 1 endpoints successfully reached the Edge routers
