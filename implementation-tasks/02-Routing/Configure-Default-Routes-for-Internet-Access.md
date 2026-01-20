# 🌐 Configure Default Routes for Internet Access

## 📌 Overview
In this task, I will configure **default routes on the core firewall (HS-CORE-FW1)** to enable **internet access** for the hospital network.

Because the hospital has **2 connections to ISP1**, I will configure **2 default route**s on the the firewall This allows outbound traffic to exit through **either ISP-facing interface**, avoiding a single point of failure.

## Reference Topology

<img width="576" height="204" alt="topology" src="https://github.com/user-attachments/assets/d7a754f8-0fff-4bb7-8631-27d07ad9e92a" />

---

## 🎯 Objectives
- Configure **primary and secondary default routes** on HS-CORE-FW1
- Enable internet-bound traffic to exit via multiple ISP paths
- Prepare the firewall for resilient internet egress

---

## 🖥 Device Involved
- **HS-CORE-FW1**

---

## 🌐 ISP-Facing Interfaces

| Interface | Role | Next-Hop |
|---------|-----|---------|
| outside (G1/8)| Primary ISP path | 69.45.12.1 |
| outside2 (G1/6) | Secondary ISP path | 69.45.12.5 |

---


## ⚙️ Default Route Configuration (HS-CORE-FW1)

Enter global configuration mode on **HS-CORE-FW1**, then configure the following default routes:

```bash
route outside 0.0.0.0 0.0.0.0 69.45.12.1
route outside2 0.0.0.0 0.0.0.0 69.45.12.5
```

**Note:** These routes allow the firewall to forward internet-bound traffic through either ISP-facing interface.

## 🧪 Verification

```bash
show route
```

<img width="567" height="59" alt="show-rotue" src="https://github.com/user-attachments/assets/15c814db-9117-427d-bdf2-89a291e9079c" />





