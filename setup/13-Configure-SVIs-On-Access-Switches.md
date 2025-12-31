# 🧩 Configure SVIs on the Access Switches (Default Gateways)

**Goal:** Configure **SVIs** on each Access Switch so VLANs have a **default gateway** for routing.

## Refernce Netork Diagram

<img width="551" height="147" alt="reference-network-diagram" src="https://github.com/user-attachments/assets/530bc025-1921-4b91-89a4-ce4868f8dffb" />

---

## 📍 SVI IP Plan

### 🟦 F1-ASW1 SVIs

| VLAN | SVI IP (Gateway) | Subnet Mask |
|---:|---|---|
| 101 | 172.16.1.1 | 255.255.255.192 |
| 110 | 172.16.1.65 | 255.255.225.224 |
| 600 | 172.16.6.1 | 255.255.225.128 |

---

### 🟩 F1-ASW2 SVIs

| VLAN | SVI IP (Gateway) | Subnet Mask |
|---:|---|---|
| 120 | 172.16.1.97 | 255.255.225.224 |
| 500 | 172.16.5.1 | 255.255.225.192 |

---

### 🟨 F2-ASW1 SVIs

| VLAN | SVI IP (Gateway) | Subnet Mask |
|---:|---|---|
| 200 | 172.16.2.1 | 255.255.225.224 |
| 220 | 172.16.1.65 | 255.255.255.224 |
| 500 | 172.16.5.1 | 255.255.255.192 |

---

### 🟥 F2-ASW2 SVIs

| VLAN | SVI IP (Gateway) | Subnet Mask |
|---:|---|---|
| 210 | 172.16.2.33 | 255.255.255.224 |
| 230 | 172.16.1.129 | 255.255.255.224 |
| 600 | 172.16.6.1 | 255.255.255.128 |

---

### 🟪 F3-ASW1 SVIs

| VLAN | SVI IP (Gateway) | Subnet Mask |
|---:|---|---|
| 300 | 172.16.3.1 | 255.255.225.192 |
| 320 | 172.16.3.97 | 255.255.255.224 |
| 330 | 172.16.3.129 | 255.255.255.224 |

---

### 🟫 F3-ASW2 SVIs

| VLAN | SVI IP (Gateway) | Subnet Mask |
|---:|---|---|
| 310 | 172.16.3.65 | 255.255.255.224 |
| 330 | 172.16.3.129 | 255.255.255.224 |
| 500 | 172.16.5.1 | 255.255.255.192 |
| 600 | 172.16.6.1 | 255.255.255.128 |

---

## 🛠️ Step-by-Step Configuration

### 1️⃣ Enter global configuration mode

```bash
enable
conf t
```

### 2️⃣ Create the SVIs listed for that switch

#### ♦️ Use this pattern for each VLAN:

```bash
interface vlan <VLAN>
ip address <IP> <MASK>
no shutdown
exit
```

**Note: sicne you will be typing many IP addresses pay close attention**

### 3️⃣ Save

```bash
end
write memory
```

## ✅ Verification
### 4️⃣ Confirm SVIs are up




