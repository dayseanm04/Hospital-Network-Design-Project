# ⏱️ 03 – Enable Syslog Timestamps on Network Devices

In this task, I will enable **timestamps on syslog messages** across all network devices.  
Including timestamps ensures logs clearly show **when events occur**, which is critical for **troubleshooting, monitoring, and auditing**.

---

## 🎯 Objective

- ✅ Enable **date and time** on all syslog messages  
- ✅ Include **milliseconds** for precise event tracking  

---

## 🖥️ Devices

This configuration is applied to **all network devices**, including:

- Core Router (`HS-CORE-R1`)
- Distribution Switches (`DSW1`, `DSW2`)
- Access Switches (`F1-ASW1`, `F1-ASW2`)
- Access Switches (`F2-ASW1`, `F2-ASW2`)
- Access Switches (`F3-ASW1`, `F3-ASW2`)
- Service Access Switch (`Service-ASW`)

---

## Reference Network

<img width="824" height="486" alt="05-Network-Diagram" src="https://github.com/user-attachments/assets/a5a199dd-c7d5-49ed-8cf4-5e41cfb4fc9f" />

## ⚙️ Configuration Steps

### 1️⃣ Enter Global Configuration Mode

```bash
enable
configure terminal
```

### 2️⃣ Enable Syslog Timestamps

```bash
service timestamps log datetime msec
```







