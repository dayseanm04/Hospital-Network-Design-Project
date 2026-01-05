# 🧩 Services Tests

## 📌 Overview

This **Services Tests** folder contains **validation tests for core network services** used in the Hospital Network Design project.

These tests confirm that **essential services function correctly across VLANs, floors, and departments**, ensuring the network can properly support hospital operations and end users.

---

## 🛠️ Services Tested
This folder currently includes tests for:

- **DHCP (Dynamic Host Configuration Protocol)**  
  - Verifies that end devices in multiple **VLANs and subnets** can automatically receive:
    - IP address  
    - Subnet mask  
    - Default gateway  

Additional service tests (such as NTP, SNMP, or Syslog) will be added in future project evolves.

---

## 📂 Folder Contents

| File | Description |
|----|------------|
| - **[DHCP-Verify-DHCP-IP-Address-Assignment-Across-VLANs.md](./DHCP-Verify-DHCP-IP-Address-Assignment-Across-VLANs.md)**
](./DHCP-Verify-DHCP-IP-Address-Assignment-Across-VLANs.md) | Confirms DHCP clients across different floors and departments successfully obtain IP addresses |

---

## 🧪 Testing Approach

Service tests are performed by:
- Initiating client-side requests (e.g., `ipconfig /renew`)
- Verifying correct IP addressing based on VLAN and subnet design
- Capturing results as **proof of successful service operation**
