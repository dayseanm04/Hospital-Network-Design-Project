# 🌐 VLAN Design

Each department is placed in its own VLAN with a matching subnet from the IP Addressing Plan.  
The **default gateway is always the first usable IP address in each subnet**.

---

## 🧱 Floor 1 – Emergency & Patient Access (172.16.1.0/24)

| VLAN ID | Department                    | Subnet             | Mask               | Default Gateway    |
|--------:|-------------------------------|--------------------|--------------------|--------------------|
| 101     | Emergency Department          | 172.16.1.0/26      | 255.255.255.192    | 172.16.1.1         |
| 105     | X-Ray / Imaging               | 172.16.1.64/27     | 255.255.255.224    | 172.16.1.65        |
| 110     | Security / Safety Office      | 172.16.1.96/28     | 255.255.255.240    | 172.16.1.97        |
| 120     | ED Nurse Station 1            | 172.16.1.112/28    | 255.255.255.240    | 172.16.1.113       |
| 130     | ED Reception                  | 172.16.1.128/28    | 255.255.255.240    | 172.16.1.129       |
| 140     | Pharmacy                      | 172.16.1.144/28    | 255.255.255.240    | 172.16.1.145       |
| 150     | Main Lobby Reception          | 172.16.1.160/28    | 255.255.255.240    | 172.16.1.161       |
| 160     | Loading Dock / Supply         | 172.16.1.176/28    | 255.255.255.240    | 172.16.1.177       |
| 170     | Security Station (Floor 1)    | 172.16.1.192/28    | 255.255.255.240    | 172.16.1.193       |
| 180     | ED Nurse Station 2            | 172.16.1.208/28    | 255.255.255.240    | 172.16.1.209       |

---

## 🧱 Floor 2 – Administration, HR & IT (172.16.2.0/24)

| VLAN ID | Department                    | Subnet             | Mask               | Default Gateway    |
|--------:|-------------------------------|--------------------|--------------------|--------------------|
| 200     | Medical Records / HIM         | 172.16.2.0/27      | 255.255.255.224    | 172.16.2.1         |
| 210     | Billing & Finance             | 172.16.2.32/27     | 255.255.255.224    | 172.16.2.33        |
| 220     | Human Resources (HR)          | 172.16.2.64/27     | 255.255.255.224    | 172.16.2.65        |
| 230     | Supply Chain / Purchasing     | 172.16.2.96/28     | 255.255.255.240    | 172.16.2.97        |
| 240     | Floor 2 Reception             | 172.16.2.112/28    | 255.255.255.240    | 172.16.2.113       |
| 250     | Floor 2 Security Station      | 172.16.2.128/28    | 255.255.255.240    | 172.16.2.129       |
| 260     | Insurance                     | 172.16.2.144/28    | 255.255.255.240    | 172.16.2.145       |
| 270    | IT Department (user VLAN)     | 172.16.2.160/28    | 255.255.255.240    | 172.16.2.161       |

(**Note:** I will cnfigure Management VLANs for IT using a separate subnet and VLAN ID.)

---

## 🧱 Floor 3 – Inpatient Care & ICU (172.16.3.0/24)

| VLAN ID | Department                    | Subnet             | Mask               | Default Gateway    |
|--------:|-------------------------------|--------------------|--------------------|--------------------|
| 300     | Nurse Offices                 | 172.16.3.0/26      | 255.255.255.192    | 172.16.3.1         |
| 310     | ICU (Floor 3)                 | 172.16.3.64/27     | 255.255.255.224    | 172.16.3.65        |
| 320     | General Inpatient Wing (F3)   | 172.16.3.96/27     | 255.255.255.224    | 172.16.3.97        |
| 330     | Radiology / Imaging           | 172.16.3.128/27    | 255.255.255.224    | 172.16.3.129       |
| 340     | Nurse Station (Floor 3)       | 172.16.3.160/27    | 255.255.255.224    | 172.16.3.161       |
| 350     | ICU Receptionist (Floor 3)    | 172.16.3.192/28    | 255.255.255.240    | 172.16.3.193       |
| 360     | Floor 3 Receptionist          | 172.16.3.208/28    | 255.255.255.240    | 172.16.3.209       |
| 370     | Security Station (Floor 3)    | 172.16.3.224/29    | 255.255.255.248    | 172.16.3.225       |

---

## 🧱 Floor 4 – Specialty Care, Clinics & ICU (172.16.4.0/24)

| VLAN ID | Department                          | Subnet             | Mask               | Default Gateway    |
|--------:|-------------------------------------|--------------------|--------------------|--------------------|
| 400     | Primary Care                        | 172.16.4.0/26      | 255.255.255.192    | 172.16.4.1         |
| 410     | Specialty Care (Pediatrics)         | 172.16.4.64/27     | 255.255.255.224    | 172.16.4.65        |
| 420     | General Inpatient Wing (Floor 4)    | 172.16.4.96/27     | 255.255.255.224    | 172.16.4.97        |
| 430     | ICU (Floor 4)                       | 172.16.4.128/27    | 255.255.255.224    | 172.16.4.129       |
| 440     | Phlebotomy / Blood Draw             | 172.16.4.160/28    | 255.255.255.240    | 172.16.4.161       |
| 450     | Nurse Station (Floor 4)             | 172.16.4.176/28    | 255.255.255.240    | 172.16.4.177       |
| 460     | ICU Receptionist (Floor 4)          | 172.16.4.192/28    | 255.255.255.240    | 172.16.4.193       |
| 470     | Specialty Care Receptionist         | 172.16.4.208/28    | 255.255.255.240    | 172.16.4.209       |
| 480     | Primary Care Receptionist           | 172.16.4.224/28    | 255.255.255.240    | 172.16.4.225       |
| 490     | Security Station (Floor 4)          | 172.16.4.240/29    | 255.255.255.248    | 172.16.4.241       |

## ✅ Summary

- Each department has:
  - Its **own VLAN ID**
  - A subnet from the **IP Addressing Plan**
  - A **default gateway** set to the first usable IP
- Floors are separated by:
  - Different **172.16.x.0/24** networks
  - VLANs that match the department structure
- This design makes it easy to:
  - Apply ACLs between VLANs
  - Prioritize traffic (ED, ICU, Imaging)
  - Troubleshoot issues by floor or department

This VLAN design will be used when configuring **SVIs on the Layer 3 switch**, **inter-VLAN routing**, and **ACLs** in the configuration phase.

---

**Note: I will make changes when necessary**
