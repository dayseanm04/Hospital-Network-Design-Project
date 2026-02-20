# 🌐 05 – Configure Static Routes to INET Web Server Network

In this task, I configure **static routes** on the hospital edge routers so the **hospital LAN can reach the INET web server subnet (70.70.70.0/24)**.  

I am using **static routing** to demonstrate external network reachability.

## Topology For Reference

<img width="922" height="582" alt="1" src="https://github.com/user-attachments/assets/c963c9d8-f69c-45e9-a509-d40216b576c6" />

## 🎯 Objectives

- Configure static routes on HS-EDGE-R1 and HS-EDGE-R2
- Ensure reachability to VLAN 222 (INET Web Servers)

---

## 🧠 Network Overview

| Subnet | Purpose |
|--------|----------|
| 70.70.70.0/24 | INET Web Server Network (VLAN 222) |
