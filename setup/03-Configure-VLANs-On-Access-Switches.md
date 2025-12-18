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

| VLAN ID | VLAN Name | Access Ports |
|--------:|-----------|--------------|
| 101 | Emergency-Dept | Gi1/0/1 – Gi1/0/8 |
| 110 | X-Ray-Imaging-DPT | Gi1/0/9 – Gi1/0/16 |
| 600 | F1-Receptionists | Gi1/0/17 – Gi1/0/20 |


## 🧩 Floor 1 – F1-ASW2

| VLAN ID | VLAN Name | Access Ports |
|--------:|-----------|--------------|
| 101 | Emergency-Dept | Gi1/0/1 – Gi1/0/6 |
| 120 | Nurse-Stations | Gi1/0/7 – Gi1/0/11 |
| 140 | Pharmacy | Gi1/0/12 – Gi1/0/14 |
| 180 | Supply-Chain-Purchasing | Gi1/0/15 – Gi1/0/17 |
| 500 | F1-Security-Office-Station | Gi1/0/18 – Gi1/0/20 |

---

# 🏥 Floor 2 — Access Switches

## 🧩 Floor 2 – F2-ASW1

| VLAN ID | VLAN Name | Access Ports |
|--------:|-----------|--------------|
| 200 | Medical-Records-Dept | Gi1/0/1 – Gi1/0/6 |
| 210 | Billing-Finance-DPT | Gi1/0/7 – Gi1/0/12 |
| 220 | Human-Resources | Gi1/0/13 – Gi1/0/17 |
| 500 | F2-Security-Station | Gi1/0/18 – Gi1/0/20 |


---

## 🧩 Floor 2 – F2-ASW2

| VLAN ID | VLAN Name | Access Ports |
|--------:|-----------|--------------|
| 200 | Medical-Records-Dept | Gi1/0/1 – Gi1/0/4 |
| 210 | Billing-Finance-DPT | Gi1/0/5 – Gi1/0/8 |
| 230 | Insurance-DPT | Gi1/0/9 – Gi1/0/12 |
| 240 | IT-Department | Gi1/0/13 – Gi1/0/17 |
| 600 | F2-Receptionists | Gi1/0/18 – Gi1/0/20 |



