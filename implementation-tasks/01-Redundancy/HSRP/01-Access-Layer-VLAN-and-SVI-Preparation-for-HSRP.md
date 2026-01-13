# 🧱 01 – Access Layer VLAN and SVI Preparation for HSRP

In this task, I **synchronize VLANs and configure SVIs** on the **Access Layer switches** to ensure both switches on each floor have **matching VLANs and correct gateway interfaces**.  
This step prepares the access layer for **HSRP** by standardizing VLAN and SVI IP addressing.

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




 
