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

#### 2️⃣ Configure the ports as access ports 
`switchport mode access`

#### 3️⃣ Assign ports to the VLAN
`switchport access vlan [VLAN_ID]`

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

# 🏥 Floor 2 Access Switches

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

---

# 🏥 Floor 3 Access Switches

## 🧩 Floor 3 – F3-ASW1

| VLAN ID | VLAN Name | Access Ports |
|--------:|-----------|--------------|
| 300 | Nurse-Offices | Gi1/0/1 – Gi1/0/5 |
| 310 | ICU-DPT | Gi1/0/6 – Gi1/0/10 |
| 320 | Inpatient-DPT | Gi1/0/11 – Gi1/0/15 |
| 330 | Radiology-DPT | Gi1/0/16 – Gi1/0/20 |


---

## 🧩 Floor 3 – F3-ASW2

| VLAN ID | VLAN Name | Access Ports |
|--------:|-----------|--------------|
| 300 | Nurse-Offices | Gi1/0/1 – Gi1/0/5 |
| 310 | ICU-DPT | Gi1/0/6 – Gi1/0/10 |
| 330 | Radiology-DPT | Gi1/0/11 – Gi1/0/14 |
| 500 | F3-Security-Station | Gi1/0/15 – Gi1/0/17 |
| 600 | F3-Receptionists | Gi1/0/18 – Gi1/0/20 |

## 🔍 Verification (Run on Each Access Switch)

### ✔ Verify VLAN creation:
- `show vlan brief`
- `show interfaces status`

### ✔ Save configuration:
- `write memory`  

## VLAN verificaiton Bellow:

### F1-ASW1

<img width="924" height="208" alt="F1-ASW1-VLAN" src="https://github.com/user-attachments/assets/0b1c1864-c08c-45f3-97c6-3fb4105fefc5" />

### F1-ASW2

<img width="988" height="247" alt="F1-ASW2-VLAN" src="https://github.com/user-attachments/assets/c30d600b-cd6d-44df-8b5d-046523708fee" />

### F2-ASW1

<img width="949" height="245" alt="F2-ASW1-VLAN" src="https://github.com/user-attachments/assets/6e8f68b9-8b78-43be-9080-cbc0dc5ea6a4" />

### F2-ASW2

<img width="1001" height="225" alt="F2-ASW2-VLAN" src="https://github.com/user-attachments/assets/53fb783f-1fcd-42ea-b747-5cabc014a605" />

### F3-ASW1

<img width="1006" height="263" alt="F3-ASW1-VLAN" src="https://github.com/user-attachments/assets/2268422c-240a-45e8-b3e0-a8cc6d430408" />

### F3-ASW2

<img width="1038" height="245" alt="F3-ASW2-VLAN" src="https://github.com/user-attachments/assets/28bdc47d-4019-4fde-ba52-54a041db94c0" />
