# 🛠️ 02 Configure Syslog Server for Network Management

In this this task, I will deploy a **centralized Syslog server** to collect and manage **log messages** from network devices. Centralized logging improves **visibility**, **troubleshooting**, and **auditing** across the hospital network.

---

## 🎯 Objectives

- ✅ Deploy a dedicated **Syslog server**
- ✅ Enable **only the Syslog service**
- ✅ Assign a **static IP address** for the server

---

## Reference Network Diagram

<img width="496" height="256" alt="network-diagram" src="https://github.com/user-attachments/assets/d7fc218d-63e7-4c0a-846d-f14c73f02a24" />

## 🖥️ Syslog Server Details

| Item | Value |
|---|---|
| Server Name | `SYSLOG-SRV` |
| Connected To | `Service-ASW` |
| Switch Port | `G1/0/3` |
| Service Enabled | Syslog (only) |

---

## 🌐 IP Configuration (Static)

| Setting | Value |
|---|---|
| IP Address | `10.10.10.4` |
| Subnet Mask | `255.255.255.224` |
| Default Gateway | `10.10.10.1` |

## ⚙️ Configuration Steps

### 1️⃣ Add the Syslog Server
- Place a server in the topology
- Rename it to **`SYSLOG-SRV`**

### 2️⃣ Configure Services
- Click on **Services**
- **Disable all services**
- **Enable only Syslog**

### 3️⃣ Configure Network Settings
- Click on Desktop
- Click on  IP Configuration
- Assign the static IP information listed above



### ✅ Click ➡️ [here](/testing/04-Connectivity-Tests/08-Test-Syslog-Server-Connectivity.md) for the SYSLOG-SRV connectivity tests
