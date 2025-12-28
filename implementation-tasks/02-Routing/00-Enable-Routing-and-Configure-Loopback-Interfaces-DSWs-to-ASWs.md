# 🌐 Enable Routing and Configure Loopback Interfaces

**Purpose:** Enable **Layer 3 routing** on all Distribution and Access switches and configure **Loopback interfaces** 
used for routing, testing, and router IDs for dynamic routing protocols such as OSPF.

---

## Reference NetworkDiagram

<img width="652" height="409" alt="reference-net-diagram" src="https://github.com/user-attachments/assets/c884f583-fa21-40e8-ab5d-03bee8fb42b8" />


---

## 🧭 What I will do in this task:
- ✅ Enable **IP routing** on all ASWs, DSWs, and the Service switch  
- 🔁 Configure **Loopback0** interfaces with unique IP addresses  

---

## ✅ Devices Involved
- **Distribution Switches:** DSW1, DSW2  
- **Access Switches:**  
  - F1-ASW1, F1-ASW2  
  - F2-ASW1, F2-ASW2  
  - F3-ASW1, F3-ASW2  
  - Service-ASW

---


## 🛠️ Part 1 - Enable Layer 3 Routing

### 1️⃣ Enable routing on ALL Access and Distribution switches

#### 💠 On **each switch**, enter global configuration mode and enable routing:

```bash
ip routing
```

**✅ This allows the switches to route traffic.**

---

## 🔁 Part 2 - Configure Loopback Interfaces

**Why Loopbacks?** Loopback interfaces are always up and are commonly used for  Router IDs (OSPF), a stable management IPs and for Routing verification and testing

---

### 2️⃣ Configure Loopbacks on **Access Switches**

| Switch | Loopback IP |
|---|---|
| F1-ASW1 | 10.0.0.1/32 |
| F1-ASW2 | 10.0.0.2/32 |
| F2-ASW1 | 10.0.0.3/32 |
| F2-ASW2 | 10.0.0.4/32 |
| F3-ASW1 | 10.0.0.5/32 |
| F3-ASW2 | 10.0.0.6/32 |
| Service-ASW | 10.0.0.7/32 |


### 💠 Steps (repeat on each ASW):

```bash
interface loopback0
ip address <assigned-IP> 255.255.255.255
exit
```

### 3️⃣ Configure Loopbacks on **Distribution Switches**

| Switch | Loopback IP |
|---|---|
| DSW1 | 10.0.0.10/32 |
| DSW2 | 10.0.0.11/32 |

###  💠 Steps (repeat on each DSW):

```bash
interface loopback0
ip address <assigned-IP> 255.255.255.255
exit
```

---

## ✅ Verification

### 💠 Verify Loopback Interfaces

#### On DSW1 show ip interface brief | include Loopback

<img width="766" height="85" alt="DSW1-lo0" src="https://github.com/user-attachments/assets/b8e5333c-b96f-4503-8df3-08dc701be6ef" />

#### On DSW2 show ip interface brief | include Loopback

<img width="755" height="79" alt="DSW2-lo0" src="https://github.com/user-attachments/assets/a3b55682-45e0-43b0-ac14-7971ff85d77b" />





















