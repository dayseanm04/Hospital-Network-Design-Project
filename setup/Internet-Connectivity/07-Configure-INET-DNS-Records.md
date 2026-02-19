# 🌐 Configure INET DNS Records

In this task, I configure will **DNS records** on the **INET DNS server** so that domain names can resolve public IP addresses.  
This allows internal users (through ISP1) to access Internet services using **domain names instead of IP addresses**.


## Reference Topology

<img width="835" height="325" alt="toplogy" src="https://github.com/user-attachments/assets/fb3d5afb-915a-4c7e-b5b0-c7f570012f61" />


## 🎯 Objectives

- ✅ Create DNS A records
- ✅ Map domain names to public IP addresses

---

## 🖥️ DNS Server Information

| Item | Value |
|---|---|
| Server Name | DNS-SRV |
| IP Address | 10.20.20.10 |
| Default Gateway | 10.20.20.1 |
| Service Enabled | DNS |

---

## ⚙️ Configuration Steps (On DNS-SRV)

### 1️⃣ Configure DNS A Record

1. Open **DNS-SRV**
2. Navigate to **Services → DNS**
3. Configure a new DNS records:

## 📋 DNS Record Summary

| Domain Name | Record Type | Public IP |
|---|---|---|
| google.com | A |70.70.70.10 |
| youtube.com | A |70.70.70.20 |


###  Verification

#### ping google.com from INET-PC1

<img width="812" height="420" alt="1" src="https://github.com/user-attachments/assets/e9ceaadb-5dc0-4080-a513-c45667ffd4ce" />

