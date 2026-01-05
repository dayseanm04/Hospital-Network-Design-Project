# 🔐 Configure Username and Enable Secret for Network Devices

In this task, I configure a **local username** and an **enable secret** on all network devices. This allows secure access to **privileged EXEC mode** and supports **remote management**.

---

## 🧑‍💻 Credentials Used

| Setting | Value |
|---|---|
| Username | `daysean` |
| User Secret | `ccna` |
| Enable Secret | `ccna` |

 **⚠️ Note:** These credentials are used for **lab purposes only**. They are simple so logging in during testing is quick and easy.

---

## ⚙️ Step 1 - Enter Global Configuration Mode

### 1️⃣ Enter global config mode

```bash
enable
configure terminal
```

### 🔑 Step 2 - Configure the Enable Secret

```bash
enable secret ccna
```

### 👤 Step 3 - Create a Local Username

```bash
username bob secret ccna
```


