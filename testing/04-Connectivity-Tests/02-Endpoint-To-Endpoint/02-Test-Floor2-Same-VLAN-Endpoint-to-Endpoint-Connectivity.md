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

### 🔎 Devices Tested
- **MRD-1** (PC – DHCP)
- **MRD-PRNT** (Printer – Static)

### 📍 VLAN Information
- VLAN: **200 – Medical Records DPT**
- Subnet: **172.16.2.0/27**
- Default Gateway: **172.16.2.3**

### 🔧 Test Command

```bash
ping 172.16.2.20
```

## MRD-1 ping was successful ✅

<img width="700" height="399" alt="MRD-1" src="https://github.com/user-attachments/assets/0d0cb7f2-928d-45b6-8b7e-66b74b11ced8" />

---

## 🧪 Test 2 – Billing & Finance Department (VLAN 210)

| Device   | IP Address  | Address Type | Subnet Mask     | Default Gateway |
| -------- | ----------- | ------------ | --------------- | --------------- |
| Fin-1    | 172.16.2.37 | DHCP         | 255.255.255.224 | 172.16.2.35     |
| Fin-PRNT | 172.16.2.60 | Static       | 255.255.255.224 | 172.16.2.35     |

### 🔎 Devices Tested
- **Fin-1** (PC – DHCP)
- **Fin-PRNT** (Printer – Static)

### 📍 VLAN Information
- VLAN: **210 – Billing & Finance DPT**
- Subnet: **172.16.2.32/27**
- Default Gateway: **172.16.2.35**

```bash
ping 172.16.2.60
```

## Fin-1 ping was successful ✅

<img width="702" height="367" alt="Fin-1" src="https://github.com/user-attachments/assets/418ef628-b1a8-420d-84af-4d1ca558e538" />

---

## 🧪 Test 3 – Human Resources Department (VLAN 220)

| Device  | IP Address  | Address Type | Subnet Mask     | Default Gateway |
| ------- | ----------- | ------------ | --------------- | --------------- |
| HR-1    | 172.16.2.68 | DHCP         | 255.255.255.224 | 172.16.2.67     |
| HR-PRNT | 172.16.2.80 | Static       | 255.255.255.224 | 172.16.2.67     |

### 🔎 Devices Tested
- **HR-1** (PC – DHCP)
- **HR-PRNT** (Printer – Static)

### 📍 VLAN Information
- VLAN: **220 – Human Resources DPT**
- Subnet: **172.16.2.64/27**
- Default Gateway: **172.16.2.67**







