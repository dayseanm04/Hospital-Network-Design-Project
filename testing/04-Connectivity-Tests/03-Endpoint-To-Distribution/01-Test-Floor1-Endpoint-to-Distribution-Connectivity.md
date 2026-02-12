# 🧪 Test – Floor 1 Endpoint to Distribution Connectivity

## 📌 Purpose

This test verifies that Floor 1 endpoints can reach Distribution Switch infrastructure (DSW1 / DSW2 loopbacks and Port-Channels).

> 💡 Successful replies confirm proper Layer 3 routing from Access → Distribution layer.

## Reference Topology

<img width="1005" height="463" alt="Topology" src="https://github.com/user-attachments/assets/e5489238-85b4-4948-902c-18c321f365fb" />

---

## 🏢 Floor 1 Endpoints

| Device | VLAN | Subnet | IP Address | Connected Switch |
|--------|------|--------|------------|------------------|
| ED-1 | 101 – Emergency | 172.16.1.0/26 | 172.16.1.4 (DHCP) | F1-ASW1 |
| F1-ED-Nrs-1 | 120 – Nurses | 172.16.1.64/27 | 172.16.1.100 (DHCP) | F1-ASW2 |

Note: there are multple PCs in on Floor 1 and I some of them for demonstration. 
