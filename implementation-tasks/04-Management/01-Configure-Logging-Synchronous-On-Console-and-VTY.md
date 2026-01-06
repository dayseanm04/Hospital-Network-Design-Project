# 🖥️ Configure Logging Synchronous on Console and VTY

## 📌 Overview

I this task I will configure **logging synchronous** on both the **console** and **VTY (remote access) lines** of network devices.

`logging synchronous` prevents system messages (such as routing or interface logs) from interrupting commands while an administrator is typing in the CLI. Instead, log messages are displayed cleanly on a new line.

---

## 🎯 Objective

- Prevent log messages from interrupting CLI input
- Improve usability during console and SSH sessions
- Ensure cleaner and more readable command-line interaction

---

## 🧠 Why This Matters

Without `logging synchronous`, system messages (for example, OSPF updates) can appear **in the middle of a command**, causing:

- Confusing CLI output
- Mistyped or incomplete commands
- Reduced efficiency during troubleshooting

Enabling logging synchronous ensures a **professional and user-friendly management experience**.

---

## ⚙️ Configuration 

Apply the following configuration on **ALL network devices**.

### 1️⃣ Enter global configuration mode

```bash
enable
configure terminal
```

### 2️⃣ Configure logging synchronous on the console line

```bash
line console 0
logging synchronous
exit
```

### 3️⃣ Configure logging synchronous on VTY lines

```bash
line vty 0 15
logging synchronous
exit
```



