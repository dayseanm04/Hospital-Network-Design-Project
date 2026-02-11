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

## 🧪 Test 1 – IT to Emergency Department and F1-ED-Nrs DPT (Floor 1)

### 🔎 Destination
- ED-1 IP: **172.16.1.4 (DHCP)**
- VLAN: **101 – Emergency DPT**

### 🔎 Destination 2
- **F1-ED-Nrs-1**
- VLAN: **120 – Floor 1 Nurses DPT**
- IP: **172.16.1.100 (DHCP)**


### 🔧 Test Commands

```bash
ping 172.16.1.4
ping 172.16.1.100
```

## IT-PC1 to ED-1 and F1-ED-Nrs-1 ping was successful ✅

<img width="882" height="750" alt="IT1-ED1-ED-Nrs-1" src="https://github.com/user-attachments/assets/003b3cbc-2ab9-4332-9b32-4a9c4a838c0b" />

---

## 🧪 Test 2 – IT to Medical Records (Floor 2)

### 🔎 Destination
- **MRD-1** : 172.16.2.4 (DHCP)
- **MRD-3** : 172.16.2.6 (DHCP)
- VLAN: **200 – Medical Records DPT**


### 🔧 Test Command

```bash
ping 172.16.2.4
ping 172.16.2.6
```

## IT-PC1 to MRD-1 and MRD-3 ping was successful ✅

<img width="881" height="737" alt="IT1-MRD-1-3" src="https://github.com/user-attachments/assets/d42ec8d2-c7ad-4cb9-a749-e47b4ab08916" />


---

## 🧪 Test 3 – IT to ICU (Floor 3

### 🔎 Destination
- **ICU-3** : 172.16.2.4 (DHCP)
- VLAN: **310 – ICU DPT**

### 🔎 Destination

- **Rad-1 IP**: 172.16.3.134 (DHCP)
- VLAN: **330 – Radiology DPT**

### 🔧 Test Commands

```bash
ping 172.16.2.76 
ping 172.16.2.134
```

## IT-PC1 to ICU-3 and Rad-1 ping was successful ✅

<img width="881" height="736" alt="IT1-ICU-1-Rad-1" src="https://github.com/user-attachments/assets/874cc523-535b-4883-8fbb-0c82be9983f9" />

---

## 🎯 Overall Test Summary
IT DPT VLAN successfully reached all department VLANs
