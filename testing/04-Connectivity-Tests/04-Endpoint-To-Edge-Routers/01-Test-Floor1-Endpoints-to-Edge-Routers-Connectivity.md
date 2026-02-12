# 🧪 Test – Floor 1 Endpoints to Edge Routers Connectivity

## 📌 Purpose
This test verifies that Floor 1 endpoints can successfully reach the Edge Routers (HS-EDGE-R1 and HS-EDGE-R2).

> 💡 Successful replies confirm proper Layer 3 routing from Access → Distribution → Core → Edge.

## Reference Topology

<img width="1005" height="463" alt="Topology" src="https://github.com/user-attachments/assets/e5489238-85b4-4948-902c-18c321f365fb" />

---

## 🏢 Floor 1 Endpoints

| Device | VLAN | Subnet | IP Address | Connected Switch |
|--------|------|--------|------------|------------------|
| ED-1 | 101 – Emergency | 172.16.1.0/26 | 172.16.1.4 (DHCP) | F1-ASW1 |
| Nrs-1 | 120 – F1 Nurses | 172.16.1.96/26 | 172.16.1.102 (DHCP) | F1-ASW2 |

---

