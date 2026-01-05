# 🔐 Secure Network Devices Console Access (Username + Password)

In this task, I secured **console access** on the network devices by requiring **local username/password authentication**, setting an **idle timeout**, and limiting console sessions.

---

## ✅ What This Does

- 👤 Requires a **local user account** to log in on the console (`login local`)
- ⏳ Automatically logs out idle sessions (`exec-timeout`)
- 🚫 Limits the number of console sessions (`session-limit 1`)

**⚠️ Note:** This assumes you already created a local username (example: `username daysean secret ccna`). 

### Click here to configure local authentication ➡️ [Here](/Network-Security/01-Device-Access-Security/01-Configure-Local-Authentication-For-Network-Devices.md)


---

## 🛠️ Step 1 - Enter Global Configuration Mode

```bash
enable
configure terminal
```

## 🖥️ Step 2 — Secure the Console Line

### 1️⃣ Enter console line configuration

```bash
line console 0
```

### 2️⃣ Enable local login

```bash
login local
```

### 3️⃣ Set timeout to 4 minutes

```bash
exec-timeout 4
```

## 🔒 Step 3 - Limit Console Sessions

```bash
session-limit 1
```

### 💾 Step 4 - Save the Configuration

```bash
do write memory
```

### 🔍 Step 5 - Verify the Console Settings ✅

```bash
show run | section line con 0
```

<img width="409" height="116" alt="verify-console-config" src="https://github.com/user-attachments/assets/836df1e3-fdeb-4e8e-89c6-a8882782eee0" />
