# 🌐 Configure ISP1 to ISP2 Interconnection and Static Routes

## 📌 Overview
This task establishes a **point-to-point interconnection** between **ISP1-R1** and **ISP2-R1** using a /30 subnet.

I configured Static routes are configured on both ISP routers to allow reachability.

## Topology For Reference

<img width="380" height="376" alt="topology" src="https://github.com/user-attachments/assets/14e638b2-942a-4a57-a73e-fbf651d60806" />


---

## 🎯 Objective
- Configure ISP1 ↔ ISP2 interconnection
- Assign the 70.1.1.0/30 IP
- Configure static routes for ISP1-ISP2 reachability
- Verify connectivity using ping

---

## 🧱 Interconnection Design


| Item | Value |
|------|-------|
| Subnet | 70.1.1.0/30 |
| ISP1-R1 Interface | G1/0/1 |
| ISP1-R1 IP | 70.1.1.1/30 |
| ISP2-R1 Interface | G1/1/4 |
| ISP2-R1 IP | 70.1.1.2/30 |

---
