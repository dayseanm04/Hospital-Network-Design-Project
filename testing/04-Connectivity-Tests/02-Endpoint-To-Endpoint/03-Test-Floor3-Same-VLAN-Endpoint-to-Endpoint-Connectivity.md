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

## F3-Nrs-1 ping was successful ✅

<img width="695" height="402" alt="F3-Nrs-1" src="https://github.com/user-attachments/assets/d3937c9b-f0d7-4bf4-935c-846b537eb034" />

---

## 🧪 Test 2 – ICU Department (VLAN 310)

### 🖥️ IP Addressing

| Device | IP Address  | Address Type | Subnet Mask     | Default Gateway |
| ------ | ----------- | ------------ | --------------- | --------------- |
| ICU-1  | 172.16.3.70 | DHCP         | 255.255.255.224 | 172.16.3.67     |
| ICU-4  | 172.16.3.73 | DHCP         | 255.255.255.224 | 172.16.3.67     |

### 🔎 Devices Tested
- **ICU-1** (PC – DHCP)
- **ICU-4** (PC – DHCP)

### 📍 VLAN Information
- VLAN: **310 – ICU DPT**
- Subnet: **172.16.3.64/26**
- Default Gateway: **172.16.3.64**
- ICU-1 connected to **F3-ASW1**
- ICU-4-PRNT connected to **F3-ASW2**

### 🔧 Test Command

```bash
ping 172.16.3.73
```

## ICU-1 ping was successful ✅

<img width="707" height="406" alt="ICU-1" src="https://github.com/user-attachments/assets/245a0ed7-0960-4261-9fa4-ed56d309f06e" />

---

## 🧪 Test 3 – Radiology Department (VLAN 330)

### 🖥️ IP Addressing

| Device   | IP Address   | Address Type | Subnet Mask     | Default Gateway |
| -------- | ------------ | ------------ | --------------- | --------------- |
| Rad-1    | 172.16.3.133 | DHCP         | 255.255.255.224 | 172.16.3.131    |
| Rad-PRNT | 172.16.3.140 | Static       | 255.255.255.224 | 172.16.3.131    |

### 🔎 Devices Tested
- **Rad-1** (PC – DHCP)
- **Rad-PRNT** (Printer – DHCP)

### 📍 VLAN Information
- VLAN: **310 – ICU DPT**
- Subnet: **172.16.3.128/26**
- Default Gateway: **172.16.3.131**
- ICU-1 connected to **F3-ASW1**
- ICU-4-PRNT connected to **F3-ASW2**

### 🔧 Test Command

```bash
ping 172.16.3.73
```

## Rad-1 ping was successful ✅

<img width="696" height="397" alt="Rad-1" src="https://github.com/user-attachments/assets/2ee478a4-80a5-452b-83b9-3248418f8aab" />

---

