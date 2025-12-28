# 🔟 Configure Server VLAN on Service-ASW (VLAN 700)

I this task, I will configure VLAN for the servers that will serve **network services** such as (DHCP, DNS, NTP, etc.) for the hospital.

---

## 🌐 VLAN / Subnet Details
| Item | Value |
|---|---|
| VLAN ID | **700** |
| VLAN Name | **Servers** |
| Subnet | **10.10.10.0/27** |
| Subnet Mask | **255.255.255.224** |
| First Usable IP | **10.10.10.1** ✅ |
| Last Usable IP | **10.10.10.30** ✅ |
| Broadcast IP | **10.10.10.31** |


---

## 🛠️ Step-by-Step (Service-ASW)

### 1️⃣ Configure VLAN 700 and name it
In **global config mode**:

```bash 
vlan 700
name Servers
exit
```

---

### 2️⃣ Assign ports to VLAN 700 (Access Ports)

```bash
interface range g1/0/1 - 8
switchport
switchport mode access
switchport access vlan 700
end
```

---

### 3️⃣ Create the SVI for VLAN 700 (Gateway)
In **Global config mode**:

```bash
interface vlan 700
description SRV-VLAN-Gateway
ip address 10.10.10.1 255.255.255.224
no shutdown
end
```

✅ This makes **10.10.10.1** the **default gateway** for servers in VLAN 700.

---

## ✅ Verification

### show vlan brief

<img width="912" height="278" alt="Service-ASW-verify-vlan700" src="https://github.com/user-attachments/assets/96a52253-e9a3-4321-886f-2dd3fc19f200" />


## 💾 Save the configuration

```bash
write memory
```
