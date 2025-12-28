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
