# 🧩 DHCP – Verify DHCP IP Address Assignment Across VLANs

## 📌 Overview

This test verifies that the **DHCP service is functioning correctly across multiple VLANs and floors** in the Hospital Network Design project.

The goal is to confirm that **end devices in different departments automatically receive valid IP addressing information** without manual configuration.

---

## 🎯 Test Objective
Ensure that DHCP clients in various **VLANs and subnets** successfully receive:
- IP address
- Subnet mask
- Default gateway

This confirms that DHCP relay and routing are working correctly across the network.

---

## 🧪 Test Method

### 🔷 For each selected end device:

1. Open the **Command Prompt**
2. Run: **ipconfig /renew**
3. Verify that the device receives an IP address within the correct subnet for its VLAN

## 🏥 DHCP Verification Results

### 📍 Floor 1 Test 

#### 🔶 ED-1 ipconfig /renew

<img width="597" height="310" alt="ED1-DHCP-success" src="https://github.com/user-attachments/assets/6e5518ad-f653-47dc-9f80-40d41c89ecc8" />

#### 🔶 X-R-1 ipconfig /renew

<img width="621" height="315" alt="X-Ray1-DHCP-success" src="https://github.com/user-attachments/assets/98556f55-deb8-451d-9c1a-3105569dce33" />

### 📍 Floor 1 Test summary

| Department | Device | VLAN | Subnet | Result |
|----------|-------|------|--------|--------|
| Emergency | ED-1 | VLAN 101 | 172.16.1.0/26 | ✅ IP assigned |
| X-Ray | X-R-1 | VLAN 110 | 172.16.1.64/27 | ✅ IP assigned |

---

### 📍 Floor 2 Test

#### 🔶 MRD-1 ipconfig /renew

<img width="656" height="282" alt="MRD1-DHCP-success" src="https://github.com/user-attachments/assets/434401a4-77a8-4313-84d6-3d9750573f45" />

#### 🔶 Fin-1 ipconfig /renew

<img width="743" height="297" alt="Fin1-DHCP-success" src="https://github.com/user-attachments/assets/7898a473-2fc7-4db5-9237-9911b0f9d7a7" />

#### 🔶 HR-1 ipconfig /renew

<img width="741" height="314" alt="HR1-DHCP-success" src="https://github.com/user-attachments/assets/936cd6df-61a4-4f6c-be0a-625297e602b4" />

### 📍 Floor 2 Test summary

| Department | Device | VLAN | Subnet | Result |
|----------|-------|------|--------|--------|
| Medical Records | MRD-1 | VLAN 200 | 172.16.2.0/27 | ✅ IP assigned |
| Finance | FIN-1 | VLAN 210 | 172.16.2.32/27 | ✅ IP assigned |
| Human Resources | HR-1 | VLAN 220 | 172.16.2.64/27 | ✅ IP assigned |

---

### 📍 Floor 3 Test

#### 🔶 F3-Nrs-1 ipconfig /renew

<img width="699" height="317" alt="F3-Nrs1-DHCP-success" src="https://github.com/user-attachments/assets/512c1548-c65e-4534-86c9-d652949b6f51" />

#### 🔶 ICU-1 ipconfig /renew

<img width="743" height="316" alt="ICU1-DHCP-success" src="https://github.com/user-attachments/assets/02bb7bad-d824-41ad-923f-888dcd67de0e" />

#### 🔶 Rad-1 ipconfig /renew

<img width="612" height="310" alt="Rad1-DHCP-success" src="https://github.com/user-attachments/assets/6eb230f7-ddde-4c22-94f5-c9a7ca754e78" />













