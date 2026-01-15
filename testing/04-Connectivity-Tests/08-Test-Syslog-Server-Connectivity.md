# 🧪 08 – Test Syslog Server Connectivity

In this test I will verify **network connectivity** between the **Syslog server** and key network devices.  

Successful tests confirm the server is **reachable** and ready to receive syslog messages.


## 🎯 Test Objectives

- ✅ Confirm the Syslog server can reach its **default gateway**
- ✅ Verify **Distribution Switches** can reach the Syslog server

---

## Reference Network Diagram

<img width="496" height="256" alt="network-diagram" src="https://github.com/user-attachments/assets/d7fc218d-63e7-4c0a-846d-f14c73f02a24" />

---

## 🖥️ Devices Involved

| Device | Role |
|---|---|
| `SYSLOG-SRV` | Centralized logging server |
| `Service-ASW` | Access switch for management services |
| `DSW1` | Distribution switch |

---
