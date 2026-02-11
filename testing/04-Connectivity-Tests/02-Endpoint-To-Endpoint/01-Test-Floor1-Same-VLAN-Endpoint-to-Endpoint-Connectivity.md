# 🧪 Test – Floor 1 Same VLAN Endpoint-to-Endpoint Connectivity

## 📌 Purpose

This test verifies **intra-VLAN connectivity** between endpoints in the **same VLAN** on Floor 1.

> 💡 These tests confirm that devices within the same broadcast domain can communicate properly across access switches (F1-ASW1 and F1-ASW2).

## Reference Topology

<img width="1005" height="463" alt="Topology" src="https://github.com/user-attachments/assets/e5489238-85b4-4948-902c-18c321f365fb" />

---

### 🖥️ IP Addressing

| Device | IP Address | Address Type | Subnet Mask | Default Gateway |
|---------|------------|--------------|-------------|-----------------|
| ED-1 | 172.16.1.4 | DHCP | 255.255.255.192 | 172.16.1.3 |
| ED-PRNT | 172.16.1.31 | Static | 255.255.255.192 | 172.16.1.3 |
