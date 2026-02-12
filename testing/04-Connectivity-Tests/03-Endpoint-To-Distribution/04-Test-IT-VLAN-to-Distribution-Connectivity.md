# 🧪 Test – IT VLAN to Distribution Connectivity

## 📌 Purpose
This test verifies that the **IT Department VLAN (VLAN 240)** can successfully reach the **Distribution Layer (DSW1 / DSW2)** including loopback interfaces and port-channels.

## 💡 Successful replies confirm:
- Layer 3 routing from IT VLAN to Distribution layer
- Redundant paths to DSW1 and DSW2
-  Proper core/distribution reachability

## Reference Topology

<img width="1005" height="463" alt="Topology" src="https://github.com/user-attachments/assets/e5489238-85b4-4948-902c-18c321f365fb" />

---

# 🏢 Source Endpoint – IT Department

| Device | VLAN | Subnet | IP Address | Address Type | Connected Switch |
|--------|------|--------|------------|--------------|------------------|
| IT-PC1 | 240 – IT DPT | 10.50.50.0/26 | 10.50.50.2 | Static | Service-ASW |

---

# 🌐 Distribution Infrastructure Targets

| Target Device | Interface Type | IP Address |
|---------------|---------------|------------|
| DSW1 | Loopback | 10.0.0.10 |
| DSW1 | Port-Channel | 10.255.2.1 |
| DSW2 | Loopback | 10.0.0.11 |
| DSW2 | Port-Channel | 10.255.2.6 |


