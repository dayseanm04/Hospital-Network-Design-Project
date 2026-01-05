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

## 🛠️ Step 1 — Enter Global Configuration Mode

```plaintext
enable
configure terminal
