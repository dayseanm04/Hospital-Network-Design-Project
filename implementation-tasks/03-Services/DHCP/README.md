# 🌐 DHCP Service – Implementation Tasks

## 📌 Overview

This folder contains the **implementation tasks for the DHCP service** in the Hospital Network Design project.

These steps focus on **deploying, configuring, and integrating a centralized DHCP server** so end devices across multiple departments and VLANs can automatically receive IP addressing information.


---

## 🛠️ DHCP Implementation Tasks

| Step | Task | Description |
|----|----|----|
| 01 | **[Connect DHCP Server to Service-ASW](./01-Connect-DHCP-Server-To-Service-ASW.md)** | Physically connects the DHCP server to the service access switch |
| 02 | **[Configure DHCP Server IP and Gateway](./02-Configure-DHCP-Server-IP-and-Gateway.md)** | Assigns a static IP address and default gateway to the DHCP server |
| 03 | **[Configure DHCP Scopes for Hospital Departments](./03-Configure-DHCP-Scopes-For-Hospital-Departments.md)** | Creates DHCP scopes for department VLANs and subnets |
| 04 | **[Configure DHCP Relay for Access Layer VLANs](./04-Configure-DHCP-Relay-For-Access-Layer-VLANs.md)** | Enables DHCP relay so VLANs can reach the centralized DHCP server |

---

## 🎯 Purpose
The DHCP service ensures:

- Automatic IP address assignment
- Consistent subnet and gateway configuration
- Scalable network expansion
- Reduced manual configuration errors

---

## 📝 Notes

- DHCP testing and verification are documented separately in the **Services-Tests** folder
- Additional DHCP enhancements may be added in later project stages
