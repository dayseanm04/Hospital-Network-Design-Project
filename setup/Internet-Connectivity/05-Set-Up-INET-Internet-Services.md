# 🌐 05 – Set Up INET Internet Services

## Reference Topology

<img width="835" height="325" alt="toplogy" src="https://github.com/user-attachments/assets/fb3d5afb-915a-4c7e-b5b0-c7f570012f61" />

## 📌 Overview
This task, I will setup the **INET servers** to simulate public internet services.

The will enable the following services:

- DNS
- NTP
- HTTP and HTTPS

These services are will be used to test internet connectivity from the hospital LAN.


## 🎯 Objectives
- Enable DNS service on INET server
- Enable NTP service for time synchronization
- Enable HTTP and HTTPS for web access
- Prepare internet simulation environment

# 🧱 INET Server Services Setup

## 1️⃣ Enable NTP Service

On the INET Server:
- Navigate to **Services**
- Select **NTP**
- Turn **NTP Service ON**
- Turn off every other service

<img width="812" height="487" alt="NTP" src="https://github.com/user-attachments/assets/91472d1e-9577-404f-be0f-72b6c623dd14" />

### 📝 Purpose
Allows hospital devices to synchronize time from an external source.


##  2️⃣ Enable DNS Service

On the INET Server:
- Navigate to **Services**
- Select **DNS**
- Turn **DNS Service ON**
- Turn off every other service

<img width="786" height="446" alt="DNS-SRV" src="https://github.com/user-attachments/assets/a2e4a867-0d6c-48d6-990f-b5e5e6f80213" />

### 📝 Purpose
Resolves domain names to IP addresses for internet simulation.




