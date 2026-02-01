# 🌐 Configure Static NAT for INET Servers on ISP1-R1

In this task, I configure static NAT on ISP1-R1 so that the INET servers (DNS, HTTP, and NTP) can be reached using public IP addresses. 

## 🎯 Objectives

- ✅ Configure **inside** and **outside** NAT interfaces on ISP1-R1
- ✅ Create **static NAT mappings** for INET servers
- ✅ Verify NAT translations and connectivity


## Topology For Reference

<img width="745" height="301" alt="reference-topology" src="https://github.com/user-attachments/assets/efe4388b-2f59-4b9e-851a-c135db1689ad" />

---

## 🧠 NAT Design Overview

- **Inside (private) network:** towards the INET network  `10.20.20.0/24`
- **Outside (public) network:** towards the hospital firewall
- **NAT type:** Static

---

## 🔌 Interface Roles (ISP1-R1)

| Interface | Role |
|---|---|
| Interface toward `INET-SW` | `ip nat inside` |
| Interfaces toward `HS-CORE-FW1` | `ip nat outside` |

---







