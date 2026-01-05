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
| 120 | ED Nurse Offices | 172.16.1.96/27 | 255.255.255.224 | 172.16.1.97 | 172.16.1.97 – 172.16.1.126 | 172.16.1.127 |

---

## 🧱 Floor 2 — Administration, HR & Billing (172.16.2.0/24)

| VLAN | Department | Network / Prefix | Mask | Default GW | Usable Host Range | Broadcast |
|---:|---|---|---|---|---|---|
| 200 | Medical Records / HIM | 172.16.2.0/27 | 255.255.255.224 | 172.16.2.1 | 172.16.2.1 – 172.16.2.30 | 172.16.2.31 |
| 210 | Billing & Finance | 172.16.2.32/27 | 255.255.255.224 | 172.16.2.33 | 172.16.2.33 – 172.16.2.62 | 172.16.2.63 |
| 220 | Human Resources (HR) | 172.16.2.64/27 | 255.255.255.224 | 172.16.2.65 | 172.16.2.65 – 172.16.2.94 | 172.16.2.95 |

---

## 🧱 Floor 3 — Inpatient Care & ICU (172.16.3.0/24)

| VLAN | Department | Network / Prefix | Mask | Default GW | Usable Host Range | Broadcast |
|---:|---|---|---|---|---|---|
| 300 | Nurse Offices / Nurse Station | 172.16.3.0/26 | 255.255.255.192 | 172.16.3.1 | 172.16.3.1 – 172.16.3.62 | 172.16.3.63 |
| 310 | ICU (Floor 3) | 172.16.3.64/27 | 255.255.255.224 | 172.16.3.65 | 172.16.3.65 – 172.16.3.94 | 172.16.3.95 |
| 330 | Radiology / Imaging | 172.16.3.128/27 | 255.255.255.224 | 172.16.3.129 | 172.16.3.129 – 172.16.3.158 | 172.16.3.159 |

---
