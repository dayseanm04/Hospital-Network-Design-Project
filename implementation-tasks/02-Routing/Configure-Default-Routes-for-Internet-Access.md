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

Enter global configuration mode on **HS-CORE-FW1**, then configure the default route:

```bash
route outside 0.0.0.0 0.0.0.0 69.45.12.1
```

**Note:** This route will allow the firewall to forward internet-bound traffic to ISP1

## 🧪 Verification

```bash
show route
```

<img width="995" height="386" alt="default-route" src="https://github.com/user-attachments/assets/d4794b05-2032-4259-91a3-f521f392d9a4" />
