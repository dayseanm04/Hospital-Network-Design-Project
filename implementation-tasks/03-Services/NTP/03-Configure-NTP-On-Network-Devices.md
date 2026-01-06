# ⏱️ Configure NTP for Network Devices

## 📌 Overview
This task configures **NTP with authentication** on **network devices** so they securely synchronize time with the **internal NTP server**.

#### ♦️Time synchronization is critical for:

- Logs and auditing
- Security events
- Troubleshooting and monitoring

---

## 🎯 Objective
- Enable NTP authentication on network devices
- Configure a trusted authentication key
- Define the internal NTP server as the time source
- Verify NTP operation

---

## 🏥 NTP Configuration Details

| Item | Value |
|----|----|
| NTP Server IP | 10.10.10.3 |
| Authentication Key ID | 10 |
| Authentication Method | MD5 |
| Password | ccna |

**⚠️ Important: These values must match the configuration on the NTP server**.

---

### 1️⃣ Enter global configuration mode

```bash
enable
configure terminal
```

### 2️⃣ Enable NTP authentication

```bash
ntp authenticate
```

### 3️⃣ Configure and trust the authentication key

```bash
ntp authentication-key 10 md5 ccna
ntp trusted-key 10
```

### 4️⃣ Configure the NTP server

```bash
ntp server 10.10.10.3 key 10
```

### 5️⃣ update the calendar

```bash
ntp update-calendar
```



