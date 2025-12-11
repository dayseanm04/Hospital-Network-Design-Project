# 🌐 03 – IP Addressing Plan

For this IP addressing plan I will use **VLSM (Variable Length Subnet Masking)** to allocate the right number of IP addresses to each hospital department.
<br/>
Each floor uses a separate **/24 network**

---

# 🧩 Floor 1 – IP Addressing (172.16.1.0/24)

| Department | Subnet | Mask | Usable IP Range | Devices |
|-----------|--------|------|------------------|---------|
| Emergency Department (ED) | 172.16.1.0/26 | 255.255.255.192 | .1 – .62 | 37 |
| X-Ray / Imaging | 172.16.1.64/27 | 255.255.255.224 | .65 – .94 | 11 |
| Hospital Security/Safety Office | 172.16.1.96/28 | 255.255.255.240 | .97 – .110 | 8 |
| ED Nurse Station 1 | 172.16.1.112/28 | 255.255.255.240 | .113 – .126 | 9 |
| ED Reception | 172.16.1.128/28 | 255.255.255.240 | .129 – .142 | 7 |
| Pharmacy | 172.16.1.144/28 | 255.255.255.240 | .145 – .158 | 6 |
| Main Lobby Reception | 172.16.1.160/28 | 255.255.255.240 | .161 – .174 | 5 |
| Loading Dock / Supply | 172.16.1.176/28 | 255.255.255.240 | .177 – .190 | 6 |
| Security Station | 172.16.1.192/28 | 255.255.255.240 | .193 – .206 | 3 |
| ED Nurse Station 2 | 172.16.1.208/28 | 255.255.255.240 | .209 – .222 | 9 |

**Floor 1 Total Allocated IPs:** about 190  
**Floor 1 Total Devices:** about 100

---

# 🧩 Floor 2 – IP Addressing (172.16.2.0/24)

| Department | Subnet | Mask | Usable IP Range | Devices |
|-----------|--------|------|------------------|---------|
| Medical Records / HIM | 172.16.2.0/27 | 255.255.255.224 | .1 – .30 | 18 |
| Billing & Finance | 172.16.2.32/27 | 255.255.255.224 | .33 – .62 | 18 |
| Human Resources | 172.16.2.64/27 | 255.255.255.224 | .65 – .94 | 13 |
| Supply Chain / Purchasing | 172.16.2.96/28 | 255.255.255.240 | .97 – .110 | 6 |
| Floor 2 Reception | 172.16.2.112/28 | 255.255.255.240 | .113 – .126 | 6 |
| Security Station | 172.16.2.128/28 | 255.255.255.240 | .129 – .142 | 3 |
| Insurance | 172.16.2.144/28 | 255.255.255.240 | .145 – .158 | 7 |
| IT Department | 172.16.2.160/28 | 255.255.255.240 | .161 – .174 | 12 |

**Floor 2 Total Allocated IPs:** about 130  
**Floor 2 Total Devices:** about 86 

---

# 🧩 Floor 3 – IP Addressing (172.16.3.0/24)

| Department | Subnet | Mask | Usable IP Range | Devices |
|-----------|--------|------|------------------|---------|
| Nurse Offices | 172.16.3.0/26 | 255.255.255.192 | .1 – .62 | 30 |
| ICU (Floor 3) | 172.16.3.64/27 | 255.255.255.224 | .65 – .94 | 15 |
| General Inpatient Wing | 172.16.3.96/27 | 255.255.255.224 | .97 – .126 | 15 |
| Radiology / Imaging | 172.16.3.128/27 | 255.255.255.224 | .129 – .158 | 12 |
| Nurse Station | 172.16.3.160/27 | 255.255.255.224 | .161 – .190 | 11 |
| ICU Receptionist | 172.16.3.192/28 | 255.255.255.240 | .193 – .206 | 7 |
| Floor 3 Receptionist | 172.16.3.208/28 | 255.255.255.240 | .209 – .222 | 7 |
| Security Station | 172.16.3.224/29 | 255.255.255.248 | .225 – .230 | 3 |
| Primary Care Receptionist | 172.16.4.224/28 | 255.255.255.240 | .225 – .238 | 5 |
| Security Station | 172.16.4.240/29 | 255.255.255.248 | .241 – .246 | 3 |

**Floor 4 Total Allocated IPs:** about 214  
**Floor 4 Total Devices:** about 122  

---

# 🧩 Floor 4 – IP Addressing (172.16.4.0/24)

| Department | Subnet | Mask | Usable IP Range | Devices |
|-----------|--------|------|------------------|---------|
| Primary Care | 172.16.4.0/26 | 255.255.255.192 | .1 – .62 | 30 |
| Pediatrics (Specialty Care) | 172.16.4.64/27 | 255.255.255.224 | .65 – .94 | 26 |
| General Inpatient Wing | 172.16.4.96/27 | 255.255.255.224 | .97 – .126 | 15 |
| ICU (Floor 4) | 172.16.4.128/27 | 255.255.255.224 | .129 – .158 | 15 |
| Phlebotomy / Blood Draw | 172.16.4.160/28 | 255.255.255.240 | .161 – .174 | 9 |
| Nurse Station | 172.16.4.176/28 | 255.255.255.240 | .177 – .190 | 7 |
| ICU Receptionist | 172.16.4.192/28 | 255.255.255.240 | .193 – .206 | 7 |
| Specialty Care Receptionist | 172.16.4.208/28 | 255.255.255.240 | .209 – .222 | 5 |
| Primary Care Receptionist | 172.16.4.224/28 | 255.255.255.240 | .225 – .238 | 5 |
| Security Station | 172.16.4.240/29 | 255.255.255.248 | .241 – .246 | 3 |

**Floor 4 Total Allocated IPs:** about 214  
**Floor 4 Total Devices:** about 120  

---

# ✅ Summary of Addressing Plan

| Floor | Total IPs Allocated | Total Devices | Notes |
|-------|----------------------|---------------|--------|
| Floor 1 | 190 | about 100 | ED, Pharmacy, Imaging |
| Floor 2 | 130 | about 86 | Administrative + IT departments |
| Floor 3 | 216 | about 122 | ICU, Radiology, Nurse Stations |
| Floor 4 | 214 | about 120 | Clinics, Pediatrics, ICU |

---

# 📘 Notes

- Each floor uses its own **/24 network** to keep addressing simple.  
- I divided the using VLSM to avoid wasting IP addresses.  
- Clinical areas use larger subnets due to more devices (PCs, phones).  
- Administrative areas mostly fit into **/27** or **/28** subnets.  
- Security stations often use the smallest subnets (**/28** or **/29**).
- The devices are strictly PCs, IP Phones and printers. It dosent include hospital equipments sicns I cant simulate that in Packet Tracer

---

This IP plan will be used later in the **VLAN design**, **routing config**, and **device configuration** sections.

---

**Note: the number of divices might be off a little, it wont affect the network**
