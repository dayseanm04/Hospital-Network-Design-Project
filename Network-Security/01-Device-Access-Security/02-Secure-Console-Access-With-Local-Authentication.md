# 🔐 Secure Network Devices Console Access (Username + Password)

In this task, I secured **console access** on the network devices by requiring **local username/password authentication**, setting an **idle timeout**, and limiting console sessions.

## ✅ What This Does

- 👤 Requires a **local user account** to log in on the console (`login local`)
- ⏳ Automatically logs out idle sessions (`exec-timeout`)
- 🚫 Limits the number of console sessions (`session-limit 1`)

**⚠️ Note:** This assumes you already created a local username (example: `username daysean secret ccna`). 

### 🔷 Click here to configure local user authentication ➡️ [Here](/Network-Security/01-Device-Access-Security/01-Configure-Local-Authentication-For-Network-Devices.md)


---

## 🛠️ Step 1 - Enter Global Configuration Mode

```bash
enable
configure terminal
```

## 🖥️ Step 2 - Secure the Console Line

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

---

### Next, I will configure **SSH** on all network devices to allow **secure remote management**. SSH encrypts management traffic and replaces insecure methods such as Telnet.


## 🛠️ Step 1 Enter Global Configuration Mode

```bash
enable
configure terminal
```

## 🌍 Step 2 - Configure the Domain Name

```bash
ip domain-name hospital.daysean.com
```

## 🔑 Step 3 - Generate RSA Keys

```bash
crypto key generate rsa
```

When prompted, enter:

**2048**

#### 🔶 Note 🔶: I will use the loopback IP address on each network device for management purposes. This provides a stable and consistent IP for remote access and monitoring, even if physical interfaces go down.

---

## 🎯 What This Configuration Does

- 🌍 Defines a **domain name** (required for SSH key generation)
- 🔐 Generates **RSA keys** for encrypted communication
- ✅ Prepares devices for **SSH-based remote access**

**⚠️ Note:** This step assumes local user accounts and line security are already configured.


### Next Click ➡️ [HERE](/Network-Security/02-Access-Control-Lists/01-Restrict-SSH-Access-With-ACL-For-IT-Department.md) to continute to Secure SSH Access with ACLs!
