# Set Up Network Devices for Remote Access (SSH)

In this task, I will configure **SSH** on all network devices to allow **secure remote management**. SSH encrypts management traffic and replaces insecure methods such as Telnet.

---

## What This Configuration Does

- Defines a **domain name** (required for SSH key generation)
- Generates **RSA keys** for encrypted communication
- Prepares devices for **SSH-based remote access**

**Note:** This step assumes local user accounts and line security are already configured.

### Click here to configure local user authentication ➡️ [Here](/Network-Security/01-Device-Access-Security/01-Configure-Local-Authentication-For-Network-Devices.md)

---

## Step 1 Enter Global Configuration Mode

```bash
enable
configure terminal
```

## Step 2 - Configure the Domain Name

```bash
ip domain-name hospital.daysean.com
```

## Step 3 - Generate RSA Keys

```bash
crypto key generate rsa
```

When prompted, enter:

**2048**

#### Note: I will use the loopback IP address on each network device for management purposes. This provides a stable and consistent IP for remote access and monitoring, even if physical interfaces go down.

### Next Click ➡️ [HERE](/Network-Security/02-Access-Control-Lists/01-Restrict-SSH-Access-With-ACL-For-IT-Department.md) to Configure ACL to Restrict SSH accesss!
