# 🌐 Configure Static NAT for INET Servers on ISP1-R1

In this task, I will configure **static NAT** on **ISP1-R1** for ther **INET servers** (DNS, HTTP, NTP) using **public IP addresses**. 

Static NAT provides fixed, predictable mappings so external clients can reliably reach INET services.

## 🎯 Objectives

- ✅ Configure **inside** and **outside** NAT interfaces on ISP1-R1
- ✅ Create **static NAT mappings** for INET servers
- ✅ Verify NAT translations and connectivity

## Topology For Reference

<img width="746" height="328" alt="INET" src="https://github.com/user-attachments/assets/50ef5b6d-db82-477d-9ab8-f33c2bd1bd8c" />

---

## 🧠 NAT Design Overview

- **Inside (private) network:** INET services subnet `10.20.20.0/24`
- **Outside (public) network:** ISP-facing links toward the hospital firewall
- **NAT type:** Static

---

## 🔌 Interface Roles (ISP1-R1)

| Interface | Role |
|---|---|
| G6/0 (Interface toward `INET-SW`) | `ip nat inside` |
| G8/0 and G9/0 (Interface toward `HS-CORE-FW1`) | `ip nat outside` |

> 💡 Marking interfaces correctly is required before creating NAT rules.

---

## ⚙️ Configuration Steps (ISP1-R1)

### 1️⃣ Configure G6/0 interface as inside

### ♦️ In Global Config mode:

#### 🟢 Configure G6/0 as nat inside:

```bash
interface G6/0
ip nat inside
```

#### 🟢 Configure G8/0 and G9/0 as nat outisde side:

```bash
interface G8/0
ip nat outside
```

```bash
interface G9/0
ip nat outside
```















