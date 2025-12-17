# 03 Configure VLANs On Access Switches

## 🎯 Goal
Configure all required VLANs on the **Access Switches** in the hospital network.  
This task focuses:

- Creating and naming VLANs
- Naming the VLANS
- Assigning interfaces to the VLAN

---

## ✅ Standard VLAN Configuration Pattern

#### 1️⃣ Enter global configuration mode  
`configure terminal`

#### 2️⃣ Create the VLAN  
`vlan [VLAN_ID]`

#### 3️⃣ Name the VLAN  
`name [VLAN_NAME]`

#### 4️⃣ Exit VLAN configuration mode  
`exit`

## ✅ Standard Interface Assignment Pattern

#### 1️⃣ Enter interface configuration  
`interface range [INTERFACE_RANGE]`

#### 2️⃣ Assign VLAN  
`switchport access vlan [VLAN_ID]`

#### 3️⃣ Enable interface  
`no shutdown`

#### 4️⃣ Exit interface configuration  
`exit`

---

# 🏥 Floor 1 Access Switches

## 🧩 Floor 1 – F1-ASW1

