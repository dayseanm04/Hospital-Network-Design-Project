# 03 Configure VLANs On Access Switches

## 🎯 Goal
Configure all required VLANs on the **Access Switches** in the hospital network.  
This task focuses:

- Creating and naming VLANs
- Naming the VLANS
- Assigning interfaces to the VLAN

---

## ✅ Standard VLAN Configuration Pattern
Use this same pattern for **every VLAN** listed below:

#### 1️⃣ Enter global configuration mode  
`configure terminal`

#### 2️⃣ Create the VLAN  
`vlan [VLAN_ID]`

#### 3️⃣ Name the VLAN  
`name [VLAN_NAME]`

#### 4️⃣ Exit VLAN configuration mode  
`exit`

