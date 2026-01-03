# 📦 Configure DHCP Pools (Scopes) – DHCP Server

**Goal:** Configure DHCP pools on the **DHCP-SRV** so client devices on each floor and department automatically receive IP addresses.  

Each pool uses the **SVI (default gateway)** that was already configured on the access switches. 

### ♦️ Find it here: [Configure SVIs on ASWs)](/setup/13-Configure-SVIs-On-Access-Switches.md)

---

## 🏥 DHCP Pool Overview

### 🟦 1st Floor DHCP Pools

| VLAN | Pool Name | Default Gateway (SVI) | Subnet Mask | Start IP | Max Users |
|---|---|---|---|---|---|
| 101 | Emergency-DPT | 172.16.1.1 | 255.255.255.192 | 172.16.1.2 | 62 |
| 110 | X-Ray-DPT | 172.16.1.65 | 255.255.255.224 | 172.16.1.66 | 30 |
| 120 | F1-Nurse-Station | 172.16.1.97 | 255.255.255.224 | 172.16.1.98 | 30 |

---


### 🟩 2nd Floor DHCP Pools

| VLAN | Pool Name | Default Gateway (SVI) | Subnet Mask | Start IP | Max Users |
|---|---|---|---|---|---|
| 200 | Medical-Rec-DPT | 172.16.2.1 | 255.255.255.224 | 172.16.2.2 | 30 |
| 210 | Billing-Finance-DPT | 172.16.2.33 | 255.255.255.224 | 172.16.2.34 | 30 |
| 220 |  HR-DPT | 172.16.2.65 | 255.255.255.224 | 172.16.2.66 | 30 |
| 230 | Insurance-DPT | 172.16.2.129 | 255.255.255.224 | 172.16.2.130 | 30 |

---

### 🏥 3rd Floor VLANs
| VLAN | Department / Pool Name | Default Gateway | Subnet Mask | Start IP | Max Users |
|---|---|---|---|---|---|
| 300 | Nurses-Office-F3 | 172.16.3.1 | 255.255.255.192 | 172.16.3.2 | 62 |
| 310 | ICU-DPT | 172.16.3.65 | 255.255.255.224 | 172.16.3.66 | 30 |
| 320 | General-Inpatient-Wing | 172.16.3.97 | 255.255.255.224 | 172.16.3.98 | 30 |
| 330 | Radiology-DPT | 172.16.3.129 | 255.255.255.224 | 172.16.3.130 | 30 |


## 🛠️ Step-by-Step: Configure DHCP Pools on **DHCP-SRV**

### 1️⃣ Open the DHCP Service
- Click **DHCP-SRV**
- Go to **Services**
- Select **DHCP**
- Make sure DHCP is **ON**

---

### 2️⃣ Create a DHCP Pool (Repeat for Each VLAN)
For **each pool**, fill in:
- **Pool Name**
- **Default Gateway** (SVI IP)
- **Subnet Mask**
- **Starting IP Address**
- **Maximum Number of Users**

👉 Click **Add** after each pool.

---

### 3️⃣ Example: Emergency Department (VLAN 101)
- Pool Name: `Emergency-DPT`
- Default Gateway: `172.16.1.1`
- Subnet Mask: `255.255.255.192`
- Start IP: `172.16.1.2`
- Max Users: `62`

---

## ✅ Verification

I have to configure an IP helper-address on the Access Switches, for them to be able to forward UDP broadcast traffic !

### DHCP Pool

<img width="836" height="407" alt="DHCP-pool" src="https://github.com/user-attachments/assets/3426df09-aa6b-4098-9a8f-61a2a64f6a0c" />

