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


## 🧩 Floor 1 – F1-ASW2

| VLAN ID | VLAN Name | Access Ports |
|--------:|-----------|--------------|
| 101 | Emergency-Dept | Gi1/0/1 – Gi1/0/6 |
| 120 | Nurse-Stations | Gi1/0/7 – Gi1/0/11 |
| 140 | Pharmacy | Gi1/0/12 – Gi1/0/14 |
| 180 | Supply-Chain-Purchasing | Gi1/0/15 – Gi1/0/17 |

---

# 🏥 Floor 2 Access Switches

## 🧩 Floor 2 – F2-ASW1

| VLAN ID | VLAN Name | Access Ports |
|--------:|-----------|--------------|
| 200 | Medical-Records-Dept | Gi1/0/1 – Gi1/0/6 |
| 210 | Billing-Finance-DPT | Gi1/0/7 – Gi1/0/12 |
| 220 | Human-Resources | Gi1/0/13 – Gi1/0/17 |

---

## 🧩 Floor 2 – F2-ASW2

| VLAN ID | VLAN Name | Access Ports |
|--------:|-----------|--------------|
| 200 | Medical-Records-Dept | Gi1/0/1 – Gi1/0/4 |
| 210 | Billing-Finance-DPT | Gi1/0/5 – Gi1/0/8 |
| 230 | Insurance-DPT | Gi1/0/9 – Gi1/0/12 |

## 🧩 Service-ASW

| VLAN ID | VLAN Name | Access Ports |
|--------:|-----------|--------------|
| 240 | IT-Department |  |
| 700 | Server Vlan | |


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



## 🔍 Verification (Run on Each Access Switch)

### ✔ Verify VLAN creation:
- `show vlan brief`
- `show interfaces status`

### ✔ Save configuration:
- `write memory`  

## VLAN verificaiton Bellow:

### F1-ASW1

<img width="934" height="174" alt="F1-1" src="https://github.com/user-attachments/assets/3a974bae-978d-468e-a2ce-8b958641edf1" />

### F1-ASW2

<img width="896" height="209" alt="F1-2" src="https://github.com/user-attachments/assets/5ee08464-8d36-483d-aeb2-a2f9349064ef" />

### F2-ASW1

<img width="938" height="206" alt="F2-1" src="https://github.com/user-attachments/assets/74edeb3f-9617-4701-9845-900d61ca26ac" />

### F2-ASW2

<img width="937" height="191" alt="F2-ASW2-vlan-brief" src="https://github.com/user-attachments/assets/e51df023-05b2-46bd-a0d1-c2f1cecf0192" />


### F3-ASW1

<img width="943" height="250" alt="F3-1" src="https://github.com/user-attachments/assets/4f830f03-5f8d-40fa-8dca-1797853ba1ad" />

### F3-ASW2

<img width="942" height="194" alt="F3-2" src="https://github.com/user-attachments/assets/9e556381-2900-4a53-9420-df2a577ed3ef" />
