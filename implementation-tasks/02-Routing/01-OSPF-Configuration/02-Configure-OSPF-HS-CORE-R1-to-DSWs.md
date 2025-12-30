# 🌐 Configure OSPF (Area 0) - HS-CORE-R1 ↔ DSW1/DSW2

**Purpose:** Enable **OSPF Area 0** between **HS-CORE-R1** and the **Distribution Switches (DSW1/DSW2)** 

## Rerence Network Diagram

<img width="625" height="436" alt="reference-area" src="https://github.com/user-attachments/assets/273d6f8a-5d8a-4ebb-a749-3bc7b22df76f" />

---

| Link | Network |
|---|---|
| HS-CORE-R1 ↔ DSW1 | **10.255.0.0/30** |
| HS-CORE-R1 ↔ DSW2 | **10.255.0.4/30** | 

---


## ✅ Step-by-Step Configuration

## 🟦 HS-CORE-R1 (Enable OSPF on all DSW uplinks)

### 1️⃣ Enter OSPF process 1

#### ♦️ In global config mode:

```bash
enable
configure terminal
```

### 2️⃣ Enable OSPF for all DSW-connected interfaces (10.255.0.0/24)

```bash
network 10.255.0.0 0.0.0.255 area 0
```

✅ This enables OSPF on **all** HS-CORE-R1 interfaces that fall within **10.255.0.0/24**, including the /30 links to **DSW1** and **DSW2**.

---
