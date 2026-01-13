# 🧱 01 – Access Layer VLAN and SVI Preparation for HSRP

In this task, I **synchronize VLANs and configure SVIs** on the **Access Layer switches** to ensure both switches on each floor have **matching VLANs and correct gateway interfaces**.  
This step prepares the access layer for **HSRP** by standardizing VLAN and SVI IP addressing.

### ✅ Click ➡️ [here](/setup/03-Configure-VLANs-On-Access-Switches.md) for VLANs I configured when I started this project.


---

## 🎯 Objectives

- ✅ Ensure all required **VLANs exist** on each access switch
- ✅ Configure **SVIs** for each VLAN
- ✅ Apply a **consistent IP addressing standard**
- ✅ Prepare the access layer for **gateway redundancy (HSRP)**

---

## 🧠 SVI IP Addressing Standard

| Switch | SVI IP Assignment |
|------|-------------------|
| `F#-ASW1` | First usable IP address in the subnet |
| `F#-ASW2` | Second usable IP address in the subnet |

This approach keeps gateway addressing **clean, predictable, and easy to troubleshoot**.

---


## 🏥 Floor 1 - Emergency & Patient Services

| VLAN | Department | Subnet | F1-ASW1 SVI | F1-ASW2 SVI |
|----:|------------|--------|-------------|-------------|
| 101 | Emergency Department | 172.16.1.0/26 | 172.16.1.1 | 172.16.1.2 |
| 110 | X-Ray / Imaging | 172.16.1.64/26 | 172.16.1.65 | 172.16.1.66 |
| 120 | Nurse Station | 172.16.1.96/26 | 172.16.1.97 | 172.16.1.98 |

---

## 🏢 Floor 2 - Administration & HR

| VLAN | Department | Subnet | F2-ASW1 SVI | F2-ASW2 SVI |
|----:|------------|--------|-------------|-------------|
| 200 | Medical Records | 172.16.2.0/27 | 172.16.2.1 | 172.16.2.2 |
| 210 | Finance | 172.16.2.32/27 | 172.16.2.33 | 172.16.2.34 |
| 220 | Human Resources | 172.16.2.64/27 | 172.16.2.65 | 172.16.2.66 |

---

## 🏬 Floor 3 - Inpatient & ICU

| VLAN | Department | Subnet | F3-ASW1 SVI | F3-ASW2 SVI |
|----:|------------|--------|-------------|-------------|
| 300 | Nurse Department | 172.16.3.0/27 | 172.16.3.1 | 172.16.3.2 |
| 310 | ICU | 172.16.3.64/27 | 172.16.3.65 | 172.16.3.66 |
| 330 | Radiology | 172.16.3.128/27 | 172.16.3.129 | 172.16.3.130 |

---

## ⚙️ Configuration Template (Apply on Access Switches)

Use the following template to configure **only the VLANs and SVIs that are missing** on each access switch.

### 1️⃣ Create VLANs

```bash
conf t
vlan <VLAN-ID>
 name <VLAN-NAME>
```

### 2️⃣ Configure the SVI

```bash
interface vlan <VLAN-ID>
 ip address <SVI-IP> <SUBNET-MASK>
 no shutdown
```

### 2️⃣ Configure DHCP Relay for the Required VLANs

```bash
interface vlan <VLAN-ID>
 ip helper-address 10.10.10.2
```

## 🔍 Verification

#### 🟢 On F1-ASW1 show ip interface brief | include Vlan

<img width="853" height="117" alt="F1-ASW1" src="https://github.com/user-attachments/assets/a18662f3-2252-4707-bab5-5110736251af" />

#### 🟢 On F1-ASW2 show ip interface brief | include Vlan

<img width="812" height="116" alt="F1-ASW2" src="https://github.com/user-attachments/assets/5332bb7a-8199-4df5-9cdb-ce6e94dc9235" />

#### 🟢 On F2-ASW1 show ip interface brief | include Vlan

<img width="862" height="119" alt="F2-ASW1" src="https://github.com/user-attachments/assets/58ae3fa4-8ebb-4191-9937-b4b4d9b8c28a" />


#### 🟢 On F2-ASW2 show ip interface brief | include Vlan

<img width="826" height="118" alt="F2-ASW2" src="https://github.com/user-attachments/assets/93367c34-b1ba-4ec5-9e22-7e8b003d8096" />


#### 🟢 On F3-ASW1 show ip interface brief | include Vlan

<img width="831" height="119" alt="F3-ASW1" src="https://github.com/user-attachments/assets/fd3ee955-0390-4a6e-b1f8-8443efd44608" />

#### 🟢 On F3-ASW2 show ip interface brief | include Vlan

<img width="788" height="119" alt="F3-ASW2" src="https://github.com/user-attachments/assets/e808135b-4eea-4dbe-9a39-6392d63b2cca" />
