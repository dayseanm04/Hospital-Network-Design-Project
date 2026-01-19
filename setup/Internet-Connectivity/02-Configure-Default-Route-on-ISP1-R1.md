# 🌐 Configure Default Routes on ISP1-R1

In this task, I will configure a **static default route*s* on **ISP1-R1** so traffic destined for **unknown external networks** can be forwarded upstream.  

This allows the **INET services network** and the **hospital network (via ISP1)** to reach each other over the simulated Internet.

## 🎯 Objective

- ✅ Configure a default route on ISP1-R1

## 🧠 Routing Overview

- ISP1-R1 acts as the **gateway between for the INET network**
- A **default route (0.0.0.0/0)** is required so ISP1-R1 knows where to send traffic it does not have specific routes for

---

## Topology For Reference

<img width="746" height="328" alt="INET" src="https://github.com/user-attachments/assets/50ef5b6d-db82-477d-9ab8-f33c2bd1bd8c" />

---

## ⚙️ Configuration Steps

Enter global configuration mode on **ISP1-R1**:

```bash
configure terminal
```

#### 🟢 Configure the static default routes:

```bash
ip route 0.0.0.0 0.0.0.0 69.45.12.2
ip route 0.0.0.0 0.0.0.0 69.45.12.6
```



