# 🚨 Issue: Clients Not Receiving IP Due to Routing Issue (VLAN 101)

## 📌 Problem Description
**ED1 (Emergency DPT PC1)** connected to **F1-ASW1** could not obtain an IP address from the **DHCP-SRV**, even after configuring an **IP helper address** on **VLAN 101**.

---

## 🌐 Affected Devices
- ED1 (Emergency DPT PC1)
- F1-ASW1
- DSW1 / DSW2
- Service-ASW
- DHCP-SRV

---

## ❌ Symptoms Observed
- ED1 could not receive an IP address from DHCP (DHCP request fails **See Below**).

<img width="600" height="204" alt="ED1-DHCP-Failed" src="https://github.com/user-attachments/assets/a0e89389-4189-4af8-a1d7-1de8c1bc05fb" />

- VLAN 101 details confirmed:
  - ED1 is in **VLAN 101**
  - VLAN 101 SVI is **172.16.1.1 /26**

---


## 🔍 Troubleshooting Steps Taken

### 1️⃣ Verified DHCP-SRV IP settings
- Checked DHCP-SRV IP, subnet, and default gateway 

<img width="745" height="338" alt="DHCP-SRV-IP" src="https://github.com/user-attachments/assets/bc43b44e-15b1-4703-bf41-688c9707f51d" />

DHCP Server IP configuration is correct!

<img width="515" height="116" alt="SVI-IP" src="https://github.com/user-attachments/assets/e375aed1-a1aa-492f-8b6f-3585fe1aebae" />

VLAN 700 SVI is correct!

### 2️⃣ Checked VLAN 101 SVI status
- Confirmed the SVI is **up**

<img width="772" height="93" alt="VLAN700-SVI-up" src="https://github.com/user-attachments/assets/8788547f-907f-4452-ab19-849d5f7abb50" />

### 3️⃣ Tested reachability to the DHCP server network

#### 🔶 DHCP SRV Pinged DHCP-SRV’s default gateway (VLAN 700 SVI) → **Success**
 
<img width="737" height="370" alt="DHCP-SRV-ping-DG" src="https://github.com/user-attachments/assets/eeea1f17-d24f-472c-ba9e-7342413fae34" />

#### 🔶 Pinged DHCP-SRV from Service-ASW → **Success**

<img width="725" height="154" alt="Service-ASW-ping-DHCP" src="https://github.com/user-attachments/assets/ce04e065-ade5-4d80-ac6e-f87c26f72d00" />

#### 🔶Pinged DHCP-SRV / gateway from F1-ASW1 → **Success**

<img width="823" height="256" alt="F1-ASW1-ping-DHCP-DG" src="https://github.com/user-attachments/assets/de012b20-6c28-4376-85d4-09edad366ffb" />

#### 🔶 Pinged DHCP-SRV / gateway from DSW1 → **Success**

<img width="744" height="259" alt="DSW1-ping-DHCP-DG" src="https://github.com/user-attachments/assets/3d7ee2ef-3e16-4fff-9bed-759ff6ddec8c" />

### 4️⃣ **Checked uplinks / Port-Channels**
- Port-Channels to distribution switches → **Up**
- DSWs Port-Channels to Service-ASW → **Up** 

### 5️⃣ Reviewed routing (OSPF) for VLAN 101

- OSPF is running between Distribution and Access layer, but VLAN 101 was not being advertised because I havent enable OSPF for that subnet yet. 

---

## 🛠 Root Cause

Since I havent enable OSPF for the Deparment subnets those subnets were advertised. I should have enable ospf for the subnets before I requested IP address. I did that to desmonstrate the imporant of enabliong OSPF on network and troubleshooting anf fixing the issue.

**Result:** the DHCP discover/offer process could not complete successfully for ED1 even though the DHCP server itself was reachable.

---

## ✅ Resolution

### 1️⃣ Enable OSPF for VLAN 101 on F1-ASW1

On **F1-ASW1**, add the VLAN 101 subnet into OSPF (Area 1).

- Enter OSPF config mode:
  - `router ospf 1` 
  
- Advertise the VLAN 101 subnet (VLAN 101 SVI = 172.16.1.1 /26 → wildcard 0.0.0.63):
  - `network 172.16.1.0 0.0.0.63 area 1`  
  *(**0.0.0.63** is the wildcard for /26, and VLAN 101 is 172.16.1.1/26.)* 
  










