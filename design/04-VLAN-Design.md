# 🌐 VLAN Design

Each department is placed in its own VLAN with a matching subnet from the IP Addressing Plan.  
The **default gateway is always the first usable IP address in each subnet**.

---

## 🧱 Floor 1 – Emergency & Patient Access (172.16.1.0/24)

| VLAN ID | Department                    | Subnet             | Mask               | Default Gateway    |
|--------:|-------------------------------|--------------------|--------------------|--------------------|
| 101     | Emergency Department          | 172.16.1.0/26      | 255.255.255.192    | 172.16.1.1         |
| 110     | X-Ray / Imaging               | 172.16.1.64/27     | 255.255.255.224    | 172.16.1.65        |
| 120     | ED Nurse Offices (and 2 stations)    | 172.16.1.96/27    | 255.255.255.224    | 172.16.1.97       |
| 140     | Pharmacy                      | 172.16.1.128/28    | 255.255.255.240    | 172.16.1.129       |
| 180     | Loading Dock / Supply         | 172.16.7.0/27    | 255.255.255.224    | 172.16.7.1       |


---

## 🧱 Floor 2 – Administration, HR & IT (172.16.2.0/24)

| VLAN ID | Department                    | Subnet             | Mask               | Default Gateway    |
|--------:|-------------------------------|--------------------|--------------------|--------------------|
| 200     | Medical Records / HIM         | 172.16.2.0/27      | 255.255.255.224    | 172.16.2.1         |
| 210     | Billing & Finance             | 172.16.2.32/27     | 255.255.255.224    | 172.16.2.33        |
| 220     | Human Resources (HR)          | 172.16.2.64/27     | 255.255.255.224    | 172.16.2.65        |
| 230     | Insurance                     | 172.16.2.128/27   | 255.255.255.224    | 172.16.2.129       |
| 240    | IT Department (user VLAN)     | 172.16.2.144/28    | 255.255.255.240    | 172.16.2.145       |
| 180     | Supply Chain / Purchasing     | 172.16.7.0/27    | 255.255.255.224    | 172.16.7.1       |

---

## 🧱 Floor 3 – Inpatient Care & ICU (172.16.3.0/24)

| VLAN ID | Department                    | Subnet             | Mask               | Default Gateway    |
|--------:|-------------------------------|--------------------|--------------------|--------------------|
| 300     | Nurse Offices                 | 172.16.3.0/26      | 255.255.255.192    | 172.16.3.1         |
| 300     | Nurse Station (Floor 3)       | 172.16.3.0/26      | 255.255.255.192    | 172.16.3.1         |
| 310     | ICU (Floor 3)                 | 172.16.3.64/27     | 255.255.255.224    | 172.16.3.65        |
| 320     | General Inpatient Wing (F3)   | 172.16.3.96/27     | 255.255.255.224    | 172.16.3.97        |
| 330     | Radiology / Imaging           | 172.16.3.128/27    | 255.255.255.224    | 172.16.3.129       |

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

## 🧩 Security Stations(172.16.5.0/26) & Receptionists (172.16.6.0/26)

| VLAN ID | Department                    | Subnet             | Mask               | Default Gateway    |
|--------|-------------------------------|--------------------|--------------------|--------------------|
| 500     | Security Station   | 172.16.5.0/26   | 255.255.255.192  | 172.16.5.1  |
| 600     | Receptionists      | 172.16.6.0/25   | 255.255.255.128  | 172.16.6.1  |

## 🧩 Server VLAN

| VLAN ID | Department      | Subnet         | Mask              | Default Gateway |
|--------|------------------|----------------|-------------------|-----------------|
| 700     | Server          | 10.10.10.0/27  | 255.255.255.224   | 10.10.10.1     |


## ✅ Summary

- Each department has:
  - Its **own VLAN ID**
  - A subnet from the **IP Addressing Plan**
  - A **default gateway** set to the first usable IP
  - The receptionists are on the same vlan
  - The Security stations are on the same vlan
  
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
