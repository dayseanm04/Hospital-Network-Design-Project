# 📡 03 – Configure Network Devices to Forward Syslog

This task I will configure **all network devices** to forward syslog messages to the centralized **SYSLOG-SRV**.  

Centralized logging allows administrators to monitor events, troubleshoot issues, and audit network activity from a single location.

---

## 🎯 Objectives

- ✅ Configure all network devices to send logs to the **Syslog server**
- ✅ Set an appropriate logging severity level
- ✅ Enable logging for privileged mode events

---


## 🖥️ Syslog Server Information

| Item | Value |
|---|---|
| Syslog Server Name | `SYSLOG-SRV` |
| Syslog Server IP | `10.10.10.4` |
| Syslog Port | `514` (default) |

---

## ⚙️ Configuration Steps  
*(Apply on **all network devices**)*

### 1️⃣ Enter Global Configuration Mode

```bash
enable
configure terminal
```

### 2️⃣ Configure the Syslog SRV Destination

```bash
logging host 10.10.10.4
```

### 3️⃣ Set Logging Severity Level

```bash
logging trap debugging
```

Note: This sends every single log message it generates to the syslog server. This also means the CPU usage goes up. As the project evoles may change this config but for now its good.


### 4️⃣ Enable User Information Logging

```bash
logging userinfo
```

Note: it generates a log message every time a user successfully uses the enable command to enter privileged EXEC mode or exit it.

### 5️⃣ Save the Configuration


```bash
end
write memory
```

<img width="912" height="100" alt="log-after-syslog-srv-config" src="https://github.com/user-attachments/assets/2eea6a0a-1607-4652-a68e-773d304da95d" />


### ✅ Click ➡️ [here](/testing/05-Services-Tests/01-Test-Syslog-Log-Reception-on-SYSLOG-SRV.md) to view the `Verify Network Devices Sending Logs to SYSLOG SRV` test.
