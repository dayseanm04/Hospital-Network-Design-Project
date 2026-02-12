# 🧪 Test – Floor 3 Endpoints to Edge Routers Connectivity

## 📌 Purpose
This test verifies that Floor 3 endpoints can successfully reach the Edge Routers (HS-EDGE-R1 and HS-EDGE-R2).

> 💡 Successful replies confirm proper Layer 3 routing from Access → Distribution → Core → Edge.

## Reference Topology

<img width="784" height="639" alt="topology" src="https://github.com/user-attachments/assets/5e8733fb-7ee1-4ac0-b0b5-9877d5e5b8fc" />


---

## 🏢 Floor 3 Endpoints

| Device | VLAN | Subnet | IP Address | Connected Switch |
|--------|------|--------|------------|------------------|
| ICU-1 | 310 – ICU | 172.16.3.64/26 | 172.16.3.69 (DHCP) | F3-ASW1 |
| Rad-3 | 330 – Radiology | 172.16.3.128/26 | 172.16.3.133 (DHCP) | F3-ASW2 |

---

## 🧪 Test 1 – ICU-1 → HS-EDGE-R1

```bash
ping 10.0.0.15      # HS-EDGE-R1 Loopback
ping 10.200.0.1     # HS-EDGE-R1 Port-Channel10
```

### ICU-1 to HS-EDGE-R1 ping was successful ✅

<img width="702" height="624" alt="ICU1-HS-EDGE-R1" src="https://github.com/user-attachments/assets/b4e302fb-2921-4089-baca-64e30c2b2e0f" />

---

## 🧪 Test 2 – Rad-3 → HS-EDGE-R2

```bash
ping 10.0.0.14      # HS-EDGE-R2 Loopback
ping 10.200.0.5     # HS-EDGE-R2 Port-Channel10
```

### Rad-3 to HS-EDGE-R2 ping was successful ✅

<img width="713" height="638" alt="Rad3-HS-EDGE-R2" src="https://github.com/user-attachments/assets/6ba63f36-f4a8-4395-b423-9eb2bca7bd9c" />

---

## 🎯 Result
-  Floor 3 endpoints successfully reached Edge layer
