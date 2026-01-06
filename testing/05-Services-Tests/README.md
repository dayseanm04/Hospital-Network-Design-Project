# 🧩 Services Tests

## 📌 Overview

This **Services Tests** folder contains **validation tests for core network services** used in the Hospital Network Design project.

These tests confirm that **essential services function correctly across VLANs, floors, and departments**, ensuring the network can properly support hospital operations and end users.

---

## 🛠️ Services Tested
This folder currently includes tests for:

- **DHCP (Dynamic Host Configuration Protocol)**  
- **NTP (Network Time Protocol)**  

Additional service tests (such as NTP, SNMP, or Syslog) will be added in future project evolves.

---

## 🧪 Testing Approach

Service tests are performed by:
- Initiating client-side requests (e.g., `ipconfig /renew`)
- Verifying correct IP addressing based on VLAN and subnet design
- Capturing results as **proof of successful service operation**
