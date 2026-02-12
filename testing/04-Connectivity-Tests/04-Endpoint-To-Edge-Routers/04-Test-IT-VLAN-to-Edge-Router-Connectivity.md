# 🧪 Test – IT VLAN to Edge Router Connectivity

## 📌 Purpose
This test verifies that the **IT Department VLAN (VLAN 240)** can successfully reach the **Edge Routers (HS-EDGE-R1 and HS-EDGE-R2)**.

### 💡 Successful replies confirm:
- Layer 3 routing from IT VLAN to Edge layer
- Redundant Edge router paths are operational
- Core-to-Edge connectivity is functioning correctly

## Reference Topology

<img width="784" height="639" alt="topology" src="https://github.com/user-attachments/assets/5e8733fb-7ee1-4ac0-b0b5-9877d5e5b8fc" />

---


# 🏢 Source Endpoint – IT Department

| Device | VLAN | Subnet | IP Address | Address Type | Connected Switch |
|--------|------|--------|------------|--------------|------------------|
| IT-PC1 | 240 – IT DPT | 10.50.50.0/26 | 10.50.50.2 | Static | Service-ASW |

---

# 🌐 Edge Router

| Target Device | Interface Type | IP Address |
|---------------|---------------|------------|
| HS-EDGE-R1 | Loopback | 10.0.0.15 |
| HS-EDGE-R1 | Port-Channel10 | 10.200.0.1 |
| HS-EDGE-R2 | Loopback | 10.0.0.14 |
| HS-EDGE-R2 | Port-Channel10 | 10.200.0.5 |

---


