# 03 – VLANs IP Addressing Plan

For this IP addressing plan I will use **VLSM (Variable Length Subnet Masking)** to allocate the right number of IP addresses to each hospital department.
<br/>
Each floor uses a separate **/24 network**

---

# Floor 1 – IP Addressing (172.16.1.0/24)

| Department | Subnet | Mask | Usable IP Range | Devices | Usable IP |
|-----------|--------|------|------------------|---------|---------|
| Emergency Department (ED) | 172.16.1.0/26 | 255.255.255.192 | .1 – .62 | 37 | 62 |
| X-Ray / Imaging | 172.16.1.64/27 | 255.255.255.224 | .65 – .94 | 11 | 30 | 
| ED Nurse Offices & Station | 172.16.1.96/27 | 255.255.255.224 | .97 – .126 | 18 | 30 |
| Pharmacy | 172.16.1.128/28 | 255.255.255.240 | .129 – .142 | 6 | 14 |
| Hospital Security/Safety Office | 172.16.5.0/26  | 255.255.255.192  | .1 - .126  | 8 | 62 |
| Floor 1 Security Station  | 172.16.5.0/26  | 255.255.255.192  | .1 - .126  | 4 | 62 |
| ED Receptionist | 172.16.6.0/25 | 255.255.255.128 | .1 - .126 | 7 | 126 |
| Main Lobby Reception | 172.16.6.0/25 | 255.255.255.128 | .1 - .126 | 5 | 126|
| Loading Dock / Supply | 172.16.7.0/27 | 255.255.255.224 | .1 - .30 | 5 | 30 |



**Floor 1 Total Allocated IPs:** about 190  
**Floor 1 Total Devices:** about 100

---

# Floor 2 – IP Addressing (172.16.2.0/24)

| Department | Subnet | Mask | Usable IP Range | Devices | Usable IP |
|-----------|--------|------|------------------|---------|----------|
| Medical Records | 172.16.2.0/27 | 255.255.255.224 | .1 – .30 | 18 | 30 |
| Billing & Finance | 172.16.2.32/27 | 255.255.255.224 | .33 – .62 | 18 | 30 |
| Human Resources | 172.16.2.64/27 | 255.255.255.224 | .65 – .94 | 13 | 30 |
| Insurance | 172.16.2.128/27 | 255.255.255.224 | .97 – .126 | 12 | 30 |
| Floor 2 Reception | 172.16.6.0/25 | 255.255.255.128 | .1 - .126 | 6 | 126 |
| Supply Chain / Purchasing | 172.16.7.0/27 | 255.255.255.224 | .1 - .30 | 6 | 30 |



**Floor 2 Total Allocated IPs:** about 130  
**Floor 2 Total Devices:** about 86 

---

# Floor 3 – IP Addressing (172.16.3.0/24)

| Department | Subnet | Mask | Usable IP Range | Devices | Usable IP |
|-----------|--------|------|------------------|---------|----------|
| Nurse Offices | 172.16.3.0/26 | 255.255.255.192 | .1 – .62 | 30 | 62|
| Nurse Station | 172.16.3.0/26 | 255.255.255.192 | .1 – .62 | 11 | 62|
| ICU (Floor 3) | 172.16.3.64/27 | 255.255.255.224 | .65 – .94 | 15 | 30 |
| General Inpatient Wing | 172.16.3.96/27 | 255.255.255.224 | .97 – .126 | 15 | 30 |
| Radiology / Imaging | 172.16.3.128/27 | 255.255.255.224 | .129 – .158 | 12 | 30 |
| ICU Receptionist | 172.16.6.0/25 | 255.255.255.128 | .1 - .126 | 7 | 126 |
| Floor 3 Receptionist | 172.16.6.0/25 | 255.255.255.128 | .1 - .126| 7 | 126 |
| Primary Care Receptionist | 172.16.6.0/25 | 255.255.255.128 | .1 - .126| 5 | 126 |

**Floor 3 Total Allocated IPs:** about 214  
**Floor 3 Total Devices:** about 122  

---

# Floor 4 – IP Addressing (172.16.4.0/24)

| Department | Subnet | Mask | Usable IP Range | Devices | Usable IP |
|-----------|--------|------|------------------|---------|----------|
| Primary Care | 172.16.4.0/26 | 255.255.255.192 | .1 – .62 | 30 | 62 |
| Pediatrics (Specialty Care) | 172.16.4.64/27 | 255.255.255.224 | .65 – .94 | 26 | 30 |
| General Inpatient Wing | 172.16.4.96/27 | 255.255.255.224 | .97 – .126 | 15 | 30 |
| ICU (Floor 4) | 172.16.4.128/27 | 255.255.255.224 | .129 – .158 | 15 | 30 |
| Phlebotomy / Blood Draw | 172.16.4.160/27 | 255.255.255.224 | .161 – .190 | 9 | 30 |
| Nurse Station | 172.16.4.176/27 | 255.255.255.224 | .193 – .222 | 7 | 30 |
| ICU Receptionist | 172.16.6.0/25 | 255.255.255.192 | .1 - .127 | 7 | 126 |
| Specialty Care Receptionist | 172.16.6.0/25 | 255.255.255.192 | .1 - .126 | 5 | 126 |
| Primary Care Receptionist | 172.16.6.0/25 | 255.255.255.192 | .1 - .126 | 5 | 126 |

**Floor 4 Total Allocated IPs:** about 214  
**Floor 4 Total Devices:** about 120  

## Security Stations & Receptionists Addressing (172.16.5.0/26)

| Department | Subnet | Mask | Usable IP Range | Devices | Usable IP |
|-----------|--------|------|------------------|---------|----------|
| Security Stations (Floor 1 - 4) | 172.16.5.0/26 | 255.255.255.192 | .1 – .62 | about 20 | 62|
| Receptionists (Floor 1- 4) | 172.16.6.0/25 | 255.255.255.128 | .1 - .127 | about 30 | 126 |
| Loading Dock / Supply / Supply Chain / Purchasing  | 172.16.7.0/27 | 255.255.255.224 | .1 - .30 | about 15 | 30 |


## Servers Addressing (10.10.10.0/27)

| Department | Subnet | Mask | Usable IP Range | Devices | Usable IP |
|-----------|--------|------|------------------|---------|----------|
| Server | 10.10.10.0/27 | 255.255.255.224 | .1 – .30 | about 10 | 30|

## T Department (10.50.50.0/26)

| Department | Subnet  | Mask   | Usable IP Range | Devices | Usable IP |
|--------|--------------|----------------|-----------------|---------|-------|
| IT Department | 10.50.50.0/26  | 255.255.255.192  | .1 - .62  | about 15 | 62 |

---

# Summary of Addressing Plan

| Floor | Total IPs Allocated | Total Devices | Notes |
|-------|----------------------|---------------|--------|
| Floor 1 | 190 | about 100 | ED, Pharmacy, Imaging |
| Floor 2 | 130 | about 86 | Administrative, Finance departments |
| Floor 3 | 216 | about 122 | ICU, Radiology, Nurse Stations |
| Floor 4 | 214 | about 120 | Clinics, Pediatrics, ICU |

---

# Notes

- Each floor uses its own **/24 network** to keep addressing simple.  
- I divided the using VLSM to avoid wasting IP addresses.  
- Clinical areas use larger subnets due to more devices (PCs, phones).  
- Administrative areas mostly fit into **/27** or **/28** subnets.  
- Security stations share the same subnet **172.16.5.0/26**
- The devices are strictly PCs, IP Phones and printers. It dosent include hospital equipments sinces I cant simulate that in Packet Tracer

This IP plan will be used later in the **VLAN design**, **routing config**, and **device configuration** sections.

**Note: the number of divices might be off a little, it wont affect the network**
