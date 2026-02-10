# 🧪 Test – Floor 3 Endpoints to Default Gateway Connectivity

## 📌 Purpose
This test verifies that **Floor 3 endpoints** can successfully reach their **default gateway** within their assigned VLANs.

> 💡 Although there are multiple PCs for the VLAN in this project, I will use **some PC sper VLAN** to validate connectivity and avoid repetition.

---

## 🏢 Floor 3 VLAN Overview

| PC Name | Department | VLAN ID | Subnet | Default Gateway | Connected Switch |
|------|-----------|--------|--------|----------------|------------------|
| F3-Nrs-1 | Nurse Department | VLAN 301 | 172.16.3.0/26 | 172.16.3.3 | F3-ASW1 |
| F3-Nrs-3 | Nurse Department | VLAN 301 | 172.16.3.0/26 | 172.16.3.3 | F3-ASW2 |
| ICU-1 | ICU Department | VLAN 310 | 172.16.3.64/27 | 172.16.3.67 | F3-ASW1 |
| ICU-3 | ICU Department | VLAN 310 | 172.16.3.64/27 | 172.16.3.67 | F3-ASW2 |
| Rad-1 | Radiology Department | VLAN 320 | 172.16.3.128/27 | 172.16.3.131 | F3-ASW1 |
| Rad-3 | Radiology Department | VLAN 320 | 172.16.3.128/27 | 172.16.3.131 | F3-ASW2 |

---

