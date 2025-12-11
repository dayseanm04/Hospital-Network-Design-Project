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








