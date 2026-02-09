# 🔒 Restrict SSH Access With ACL for IT Department

In this task, I restricted **SSH (VTY) access** on **all network devices** so that **only IT Department hosts** are allowed to remotely manage the network. This improves security by ensuring that remote access is limited to authorized systems only.

---

## 🎯 Objective

- Allow **SSH access only from IT Department PCs**
- Block all other remote access attempts
- Apply the same security policy **consistently across all devices**

---

## 🧩 IT Department Hosts Allowed

| Device | IP Address |
|------|------------|
| IT-DPT PC1 | 10.50.50.2 |
| IT-DPT PC2 | 10.50.50.3 |

---

## 🛠️ Step 1 - Create a Standard ACL

#### 🔷 do this on all of the network devices

Create an access control list that **permits only IT Department IP addresses**:

```bash
ip access-list standard 1
1 permit 10.50.50.2
2 permit 10.50.50.3
3 deny any
```

**Note: this done in global config mode**

**Note: 💡 Any IP address not explicitly permitted will be denied by default.**

## 🖥️ Step 2 - Configure VTY Lines

```bash
line vty 0 15
session-limit 2
login local
transport input ssh
access-class 1 in
```

### 🔍 What this does:

- 🔐 Requires local authentication
- 🚦 Limits VTY sessions to 2
- Allows SSH access
- 🧱 Applies ACL 1 to incoming SSH connections


## ✅ Verification

### On IT-PC1

Open command prompt: ssh -l daysean 10.0.0.1 (device loopback interface)

<img width="679" height="253" alt="IT-DPT-SSH-access" src="https://github.com/user-attachments/assets/a589714a-ac4f-4854-b38d-7d3a551a375c" />

IT-PC1 sucessfully SSH into F1-ASW1

### 🔶 Note 🔶: I will use the loopback IP address on each network device for management purposes. This provides a stable and consistent IP for remote access and monitoring, even if physical interfaces go down.

### Reference loopback IPs ➡️ [Here](/docs/Loopback-Interfaces-Reference.md)

