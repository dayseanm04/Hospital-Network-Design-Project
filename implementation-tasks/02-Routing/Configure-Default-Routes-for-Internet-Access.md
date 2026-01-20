# 🌐 Configure Default Routes for Internet Access

## 📌 Overview
In this task, I will configure a **default routes on the core firewall (HS-CORE-FW1)** to enable **internet access** for the hospital network.

## Reference Topology

<img width="576" height="204" alt="topology" src="https://github.com/user-attachments/assets/d7a754f8-0fff-4bb7-8631-27d07ad9e92a" />

---

## 🎯 Objectives
- Configure **primary default route** on HS-CORE-FW1
- Enable internet-bound traffic to exit via L3 EtherChannel

---

## 🖥 Device Involved
- **HS-CORE-FW1**

---

## 🌐 ISP-Facing Interfaces

| Interface | Role | Next-Hop |
|---------|-----|---------|
| Port-Channel15 (outside) | Path to ISP1 | 69.45.12.1 |

---


## ⚙️ Default Route Configuration (HS-CORE-FW1)

Enter global configuration mode on **HS-CORE-FW1**, then configure the following default routes:

```bash
route outside 0.0.0.0 0.0.0.0 69.45.12.1 1
```

**Note:** These routes allow the firewall to forward internet-bound traffic through either ISP-facing interface.

## 🧪 Verification

```bash
show route
```

<img width="567" height="59" alt="show-rotue" src="https://github.com/user-attachments/assets/15c814db-9117-427d-bdf2-89a291e9079c" />





