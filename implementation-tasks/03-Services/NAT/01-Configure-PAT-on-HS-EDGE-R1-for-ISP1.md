# 🌐 Configure PAT on HS-EDGE-R1 for ISP1

## 📌 Overview

This task, I will configures **PAT (NAT Overload)** on **HS-EDGE-R1** to translate internal hospital networks to public IP addresses from the **ISP1 NAT pool**.

PAT allows multiple internal hosts to share a limited number of public IP addresses.

## Reference Topology

<img width="784" height="639" alt="topology" src="https://github.com/user-attachments/assets/5e8733fb-7ee1-4ac0-b0b5-9877d5e5b8fc" />

---

## 🎯 Objective
- Create ACL for internal networks to be translated
- Configure NAT inside/outside interfaces
- Configure NAT pool for ISP1

---
