# 🧪 Test – Floor 2 Same VLAN Endpoint-to-Endpoint Connectivity

## 📌 Purpose

This test verifies **intra-VLAN connectivity** between endpoints in the **same VLAN** on Floor 2.

> 💡 These tests confirm that devices within the same broadcast domain can communicate properly across access switches (F2-ASW1 and F2-ASW2).

## Reference Topology

<img width="1005" height="463" alt="Topology" src="https://github.com/user-attachments/assets/e5489238-85b4-4948-902c-18c321f365fb" />

---

# 🏢 Floor 2 – Intra-VLAN Connectivity Tests

## 🧪 Test 1 – Medical Records Department (VLAN 200)

### 🖥️ IP Addressing

| Device | IP Address | Address Type | Subnet Mask | Default Gateway |
|---------|------------|--------------|-------------|-----------------|
| MRD-1 | 172.16.2.2 | DHCP | 255.255.255.224 | 172.16.2.3 |
| MRD-PRNT | 172.16.2.20 | Static | 255.255.255.224 | 172.16.2.3 |
