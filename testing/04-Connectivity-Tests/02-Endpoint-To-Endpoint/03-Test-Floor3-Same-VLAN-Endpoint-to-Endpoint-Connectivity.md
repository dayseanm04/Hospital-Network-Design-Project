# 🧪 Test – Floor 3 Same VLAN Endpoint-to-Endpoint Connectivity

This test verifies **intra-VLAN connectivity** between endpoints in the **same VLAN** on Floor 3.

> 💡 These tests confirm that devices within the same broadcast domain can communicate properly across access switches (F3-ASW1 and F3-ASW2).

## Reference Topology

<img width="1005" height="463" alt="Topology" src="https://github.com/user-attachments/assets/e5489238-85b4-4948-902c-18c321f365fb" />

---

# 🏢 Floor 3 – Intra-VLAN Connectivity Tests

## 🧪 Test 1 – Floor 3 Nurses Department (VLAN 300)

### 🖥️ IP Addressing

| Device | IP Address | Address Type | Subnet Mask | Default Gateway |
|---------|------------|--------------|-------------|-----------------|
| F3-Nrs-1 | 172.16.3.4 | DHCP | 255.255.255.192 | 172.16.3.3 |
| F3-Nrs-PRNT | 172.16.3.30 | Static | 255.255.255.192 | 172.16.3.3 |

### 🔎 Devices Tested
- **F3-Nrs-1** (PC – DHCP)
- **F3-Nrs-PRNT** (Printer – Static)

### 📍 VLAN Information
- VLAN: **300 – Floor 3 Nurses DPT**
- Subnet: **172.16.3.0/26**
- Default Gateway: **172.16.3.3**
- F3-Nrs-1 connected to **F3-ASW1**
- F3-Nrs-PRNT connected to **F3-ASW2**

### 🔧 Test Command

```bash
ping 172.16.3.30
```


