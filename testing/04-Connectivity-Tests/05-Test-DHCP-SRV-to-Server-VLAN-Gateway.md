# 🧪 Test DHCP-SRV ↔ VLAN 700 Default Gateway Connectivity

 **Purpose:** Verify **two-way connectivity** between the **DHCP Server (DHCP-SRV)** and the **VLAN 700 SVI (default gateway)** on the Service Access Switch.

---

## Reference Test Area

<img width="483" height="147" alt="reference-net-diagram" src="https://github.com/user-attachments/assets/2bf21d56-aa81-4e1c-920f-7d48a00c57b6" />


## 🌐 Network Context (Quick Reference)
| Item | Value |
|---|---|
| VLAN | **700 – Servers VLAN** |
| VLAN 700 SVI (Gateway) | **10.10.10.1 /27** |
| DHCP-SRV IP | **10.10.10.2 /27** |

---

## ✅ Test 1: Ping Default Gateway from DHCP-SRV

### 1️⃣ Open DHCP-SRV and ping the VLAN 700 SVI

- Command: **ping 10.10.10.1**

<img width="741" height="437" alt="DHCP-SRV-default-gateway-ping" src="https://github.com/user-attachments/assets/52e6fe7e-219c-44ba-ab36-5be9b5fbb2e7" />


### 2️⃣ On Service-ASW ping DHCP-SRV

- Command: **ping 10.10.10.2**

<img width="707" height="154" alt="Service-ASW-ping-DHCP-SRV" src="https://github.com/user-attachments/assets/0c08b00c-90fa-4119-9643-59f4a45db5f4" />

### All of the ping tests were succesfull ✅✅
