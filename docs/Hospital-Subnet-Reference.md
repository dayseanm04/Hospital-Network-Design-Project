# 🧮 Subnet-Reference (Hospital Network Design)

This file is a **quick lookup** for every VLAN subnet in the hospital network:  

✅ **Network** • ✅ **Mask** • ✅ **Gateway (first usable IP)** • ✅ **Usable range** • ✅ **Broadcast**

> 💡 **Rule used:** The **default gateway is the first usable IP** in each subnet.

---

## 🧱 Floor 1 — Emergency & Patient Access (172.16.1.0/24)

| VLAN | Department | Network / Prefix | Mask | Default GW | Usable Host Range | Broadcast |
|---:|---|---|---|---|---|---|
| 101 | Emergency Department | 172.16.1.0/26 | 255.255.255.192 | 172.16.1.1 | 172.16.1.1 – 172.16.1.62 | 172.16.1.63 |
| 110 | X-Ray / Imaging | 172.16.1.64/27 | 255.255.255.224 | 172.16.1.65 | 172.16.1.65 – 172.16.1.94 | 172.16.1.95 |

---
