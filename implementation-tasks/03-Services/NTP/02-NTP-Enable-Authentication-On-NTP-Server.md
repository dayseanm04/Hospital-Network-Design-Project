# NTP – Enable Authentication on NTP Server

## Overview

 In this task I will enable **NTP authentication** on the internal NTP server to ensure that **only trusted network devices** can synchronize time.

NTP authentication helps protect the network from **unauthorized or spoofed time sources**, which is important for log accuracy, security auditing, and troubleshooting.

---

## Objective
- Enable NTP authentication on the NTP server
- Configure an authentication key
- Secure the NTP service before client-side configuration

---

## NTP Authentication Details

| Setting | Value |
|------|------|
| NTP Server | NTP-SRV |
| Authentication | Enabled |
| Key ID | 10 |
| Password | ccna |

---

## Configuration Steps

### Open the NTP Server

- Click on **NTP-SRV**
- Navigate to **Services**

---

### Enable NTP Authentication

- Select **NTP**
- Enable **Authentication**
- Configure the authentication settings:
  - **Key ID:** `10`
  - **Password:** `ccna`

<img width="740" height="317" alt="NTP-SS" src="https://github.com/user-attachments/assets/01d02ae4-3167-4770-ab34-3042fc51a1ce" />
