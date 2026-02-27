# NTP Service – Implementation Tasks

## Overview
This folder contains the **implementation tasks for the Network Time Protocol (NTP) service** in the Hospital Network Design project.

These tasks focus on **deploying an internal NTP server, securing it with authentication, and configuring network devices to synchronize time** using the trusted server.

Accurate and consistent time synchronization is critical for:

- Log accuracy
- Security auditing
- Network troubleshooting
- Event correlation across devices

---

## NTP Implementation Tasks

| Step | Task | Description |
|----|----|----|
| 01 | **[NTP Server Deployment and Initial Configuration](./01-NTP-Server-Deployment-And-Initial-Configuration.md)** | Deploys the internal NTP server, assigns IP addressing, and enables the NTP service |
| 02 | **[Enable Authentication on NTP Server](./02-NTP-Enable-Authentication-On-NTP-Server.md)** | Secures the NTP server by enabling authentication and configuring an authentication key |
| 03 | **[Configure NTP on Network Devices](./03-Configure-NTP-On-Network-Devices.md)** | Configures routers and switches to securely synchronize time with the internal NTP server |

---

## Purpose

The NTP service ensures:
- All network devices share a **consistent and trusted time source**
- Secure time synchronization using authentication
- Reliable timestamps for logs, alerts, and security events

This is especially important in a hospital environment where **accurate logging and auditing are required**.

---

## Notes

- Authentication keys must match between the NTP server and network devices

**[Click here to view NTP Testsing Folder](/testing/05-Services-Tests/NTP/)**
