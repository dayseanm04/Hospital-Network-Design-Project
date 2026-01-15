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

## 🌐 Syslog Server Connectivity Test

#### 🟢 From **SYSLOG-SRV**, ping the default gateway: ping 10.10.10.1

<img width="709" height="440" alt="syslog-ping" src="https://github.com/user-attachments/assets/3c2f6c1f-55ca-4ea1-ac00-5b57bb24427f" />

✅ The ping test was Successful!

## 🔁 Distribution Switch Connectivity Test

#### 🟢 From DSW1, ping the Syslog server: ping 10.10.10.1

<img width="708" height="129" alt="DSW1-ping-SYSLOG_SRV" src="https://github.com/user-attachments/assets/6166f49a-3130-4c41-82ef-fed7a7e95821" />

✅ The ping test was Successful!
