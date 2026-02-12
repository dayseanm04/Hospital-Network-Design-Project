# 🧪 Test – Floor 2 Endpoint to Distribution Connectivity

## 📌 Purpose

This test verifies that Floor 2 endpoints can reach Distribution Switch infrastructure (DSW1 / DSW2 loopbacks and Port-Channels).

> 💡 Successful replies confirm proper Layer 3 routing from Access → Distribution layer.

## Reference Topology

<img width="1005" height="463" alt="Topology" src="https://github.com/user-attachments/assets/e5489238-85b4-4948-902c-18c321f365fb" />

---


## 🏢 Floor 2 Endpoints

| Device | VLAN | Subnet | IP Address | Connected Switch |
|--------|------|--------|------------|------------------|
| MRD-1 | 200 – Medical Records | 172.16.2.0/27 | 172.16.2.4 (DHCP) | F2-ASW1 |
| MRD-3 | 200 – Medical Records | 172.16.2.0/27 | 172.16.2.6 (DHCP) | F2-ASW2 |


Note: there are multple PCs in on Floor 2 and I some of them for demonstration. 

