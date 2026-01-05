# ⏱️ NTP Server Deployment and Initial Configuration

## 📌 Overview

I This task I will deploy and performs the **initial configuration of an internal NTP server** for the Hospital Network Design project.

The NTP server will provide **accurate and consistent time synchronization** for network devices and services, which is essential for logging, security, and troubleshooting.

---

## 🎯 Objective

- Deploy an internal NTP server
- Enable the NTP service on the server
- Assign a static IP address
- Place the server in the **Servers VLAN**
- Prepare the server for use by network devices

## Reference Network Diagram

<img width="474" height="210" alt="reference-topology" src="https://github.com/user-attachments/assets/643ad0bb-e50a-4beb-8099-44158d59e1e8" />

---

## 🏥 NTP Server Details

| Setting | Value |
|------|------|
| Device Name | NTP-SRV |
| VLAN | Servers VLAN |
| IP Address | 10.10.10.3 |
| Subnet Mask | 255.255.255.224 |
| Default Gateway | 10.10.10.1 |
