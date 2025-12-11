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

