# 🌐 Network Devices IP Addressing Table

This document contains the **IP addresses used by all network devices** in the Hospital Network Design project.

The information is grouped by **network layer** and **type of connection** so it is easy to read, update, and troubleshoot as the network expands.

---

## 🧱 Core Layer

### 🌍 ISP ↔ Core Firewall

| Connection | Interface | IP Address | Network |
|-----------|----------|-----------|--------|
| ISP1-R1 → HS-CORE-FW1 | ISP1-R1 G9/0 | 69.45.12.1 /30 | 69.45.12.0 /30 |
| ISP1-R1 → HS-CORE-FW1 | HS-CORE-FW1 G1/08 | 69.45.12.2 /30 | 69.45.12.0 /30 |

---

### 🔐 Core Firewall ↔ Core Router

| Connection | Interface | IP Address | Network |
|-----------|----------|-----------|--------|
| HS-CORE-FW1 → HS-CORE-R1 | HS-CORE-FW1 G1/07 | 10.255.255.1 /30 | 10.255.255.0 /30 |
| HS-CORE-FW1 → HS-CORE-R1 | HS-CORE-R1 G0/0 | 10.255.255.2 /30 | 10.255.255.0 /30 |

---

## 🧭 Core Layer ↔ Distribution Layer

| Connection | Interface | IP Address | Network |
|-----------|----------|-----------|--------|
| HS-CORE-R1 → DSW1 | HS-CORE-R1 G2/0 | 10.255.0.1 /30 | 10.255.0.0 /30 |
| HS-CORE-R1 → DSW1 | DSW1 G1/1/1 | 10.255.0.2 /30 | 10.255.0.0 /30 |
| HS-CORE-R1 → DSW2 | HS-CORE-R1 G3/0 | 10.255.0.5 /30 | 10.255.0.4 /30 |
| HS-CORE-R1 → DSW2 | DSW2 G1/1/1 | 10.255.0.6 /30 | 10.255.0.4 /30 |

---

## 🏢 Distribution Layer ↔ Access Layer  
*(All links below are **Layer 3 LACP EtherChannels**)*

### 🧑‍⚕️ Floor 1

| Connection | Port-Channel | IP Address | Network |
|-----------|-------------|-----------|--------|
| DSW1 → F1-ASW1 | DSW1 Po1 | 10.10.0.1 /30 | 10.10.0.0 /30 |
| DSW1 → F1-ASW1 | F1-ASW1 Po1 | 10.10.0.2 /30 | 10.10.0.0 /30 |
| DSW2 → F1-ASW1 | DSW2 Po1 | 10.20.0.1 /30 | 10.20.0.0 /30 |
| DSW2 → F1-ASW1 | F1-ASW1 Po2 | 10.20.0.2 /30 | 10.20.0.0 /30 |
| DSW1 → F1-ASW2 | DSW1 Po2 | 10.10.0.5 /30 | 10.10.0.4 /30 |
| DSW1 → F1-ASW2 | F1-ASW2 Po1 | 10.10.0.6 /30 | 10.10.0.4 /30 |
| DSW2 → F1-ASW2 | DSW2 Po2 | 10.20.0.5 /30 | 10.20.0.4 /30 |
| DSW2 → F1-ASW2 | F1-ASW2 Po2 | 10.20.0.6 /30 | 10.20.0.4 /30 |

---

### 🏥 Floor 2

| Connection | Port-Channel | IP Address | Network |
|-----------|-------------|-----------|--------|
| DSW1 → F2-ASW1 | DSW1 Po3 | 10.10.0.9 /30 | 10.10.0.8 /30 |
| DSW1 → F2-ASW1 | F2-ASW1 Po1 | 10.10.0.10 /30 | 10.10.0.8 /30 |
| DSW2 → F2-ASW1 | DSW2 Po3 | 10.20.0.9 /30 | 10.20.0.8 /30 |
| DSW2 → F2-ASW1 | F2-ASW1 Po2 | 10.20.0.10 /30 | 10.20.0.8 /30 |
| DSW1 → F2-ASW2 | DSW1 Po4 | 10.10.0.13 /30 | 10.10.0.12 /30 |
| DSW1 → F2-ASW2 | F2-ASW2 Po1 | 10.10.0.14 /30 | 10.10.0.12 /30 |
| DSW2 → F2-ASW2 | DSW2 Po4 | 10.20.0.13 /30 | 10.20.0.12 /30 |
| DSW2 → F2-ASW2 | F2-ASW2 Po2 | 10.20.0.14 /30 | 10.20.0.12 /30 |

---

### 🏬 Floor 3

| Connection | Port-Channel | IP Address | Network |
|-----------|-------------|-----------|--------|
| DSW1 → F3-ASW1 | DSW1 Po5 | 10.10.0.17 /30 | 10.10.0.16 /30 |
| DSW1 → F3-ASW1 | F3-ASW1 Po1 | 10.10.0.18 /30 | 10.10.0.16 /30 |
| DSW2 → F3-ASW1 | DSW2 Po5 | 10.20.0.17 /30 | 10.20.0.16 /30 |
| DSW2 → F3-ASW1 | F3-ASW1 Po2 | 10.20.0.18 /30 | 10.20.0.16 /30 |
| DSW1 → F3-ASW2 | DSW1 Po6 | 10.10.0.21 /30 | 10.10.0.20 /30 |
| DSW1 → F3-ASW2 | F3-ASW2 Po1 | 10.10.0.22 /30 | 10.10.0.20 /30 |
| DSW2 → F3-ASW2 | DSW2 Po6 | 10.20.0.21 /30 | 10.20.0.20 /30 |
| DSW2 → F3-ASW2 | F3-ASW2 Po2 | 10.20.0.22 /30 | 10.20.0.20 /30 |

---

## 🧰 Distribution Layer ↔ Service Access Switch

| Connection | Port-Channel | IP Address | Network |
|-----------|-------------|-----------|--------|
| DSW1 → Service-ASW | DSW1 Po7 | 10.255.2.1 /30 | 10.255.2.0 /30 |
| DSW1 → Service-ASW | Service-ASW Po1 | 10.255.2.2 /30 | 10.255.2.0 /30 |
| DSW2 → Service-ASW | DSW2 Po7 | 10.255.2.5 /30 | 10.255.2.4 /30 |
| DSW2 → Service-ASW | Service-ASW Po2 | 10.255.2.6 /30 | 10.255.2.4 /30 |



