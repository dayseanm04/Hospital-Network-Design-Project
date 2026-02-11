# 🧪 Test – IT DPT VLAN to Hospital Endpoint Connectivity

## 📌 Purpose
This test verifies **Layer 3 (Inter-VLAN) connectivity** from the **IT Department VLAN (VLAN 240)** to endpoints across all hospital department VLANs.


###  Successful results confirm:
- Inter-VLAN routing is functioning correctly
- OSPF outing paths are operational

## Reference Topology

<img width="1005" height="463" alt="Topology" src="https://github.com/user-attachments/assets/e5489238-85b4-4948-902c-18c321f365fb" />

---

# 🌐 Source VLAN Information

### 🔎 Source Device
- **IT-PC1**
- VLAN: **240 – IT Department**
- Subnet: **10.50.50.0/26**
- IP Address: **10.50.50.2 (Static)**
- Connected to: **Service-ASW**

---

# 🏥 Inter-VLAN Connectivity Tests

## 🧪 Test 1 – IT to Emergency Department (Floor 1)

### 🔎 Destination
- **ED-1**
- VLAN: **101 – Emergency DPT**
- IP: **172.16.1.4 (DHCP)**

### 🔎 Destination
- **F1-ED-Nrs-1**
- VLAN: **120 – Floor 1 Nurses DPT**
- IP: **172.16.1.100 (DHCP)**


### 🔧 Test Command

```bash
ping 172.16.1.4 & ping 172.16.1.100
```





