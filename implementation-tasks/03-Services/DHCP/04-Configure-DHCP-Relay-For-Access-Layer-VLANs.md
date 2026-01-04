# 📡 Configure DHCP Relay For Access Layer VLANs.md

The Distribution Switches to Access Switches connected are Layer 3 Etherchannel, The Access Switches doesnt not Foward broadcast to the Distributon Switches!

`ip helper-address` will forwards DHCP boadcast to the DHCP server.


## Reference Network Diagram

<img width="744" height="152" alt="reference-diagram" src="https://github.com/user-attachments/assets/0c90204a-c658-4b00-9081-f7736323d8ad" />

## 🧠 DHCP Server Info

| DHCP | IP Address |
|---|---|
| DHCP-SRV IP | **10.10.10.2** |

---

## 🏢 VLANs That Require DHCP Relay

### 🟦 Floor 1
- VLAN 101 (Emergency)
- VLAN 110 (X-Ray)
- VLAN 120 (Nurse Station)

### 🟩 Floor 2
- VLAN 200 (Medical Records)
- VLAN 210 (Billing)
- VLAN 220 (HR)

### 🟨 Floor 3
- VLAN 300 (Nurses Office)
- VLAN 310 (ICU)
- VLAN 330 (Radiology)

---

## 🛠️ Step-by-Step Config

### 1️⃣ Enter global configuration mode

On **each Access Switch**:

```bash
enable
configure terminal
```

---

### 2️⃣ Configure DHCP relay on client VLAN SVIs

For **each VLAN listed above**, use this pattern:

```bash
interface vlan <VLAN-ID>
ip helper-address 10.10.10.2
```

### 3️⃣ Exit and save

```bash
end
write memory
```


### 🔷 Note 🔷 I did not configure the IP helper address for every single VLAN because the goal was to demonstrate how DHCP relay works, which has already been shown. Repeating the same ip helper-address configuration on every VLAN would be repetitive and would not add additional value to the project.


