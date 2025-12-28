# 🧭 01 Configure OSPF on HS CORE FW1 and HS CORE R1.md

**Goal:** Enable **OSPF Area 0 (backbone)** between **HS-CORE-FW1** and **HS-CORE-R1** over the **10.255.255.0/30** link. 


## 🗺️ Important Note
- **HS-CORE-FW1 G1/8** connects to **ISP1-R1**, so **do NOT run OSPF** on that interface/network.  
  - ISP link: **69.45.1.0/30** 

## Reference Network Diagram

<img width="534" height="258" alt="reference-network-digram" src="https://github.com/user-attachments/assets/29724aeb-e70a-4251-8dcf-6a96203ba71d" />

---

## 🌐 OSPF Link Information
| Link | Network | Area |
|---|---|---|
| HS-CORE-FW1 ↔ HS-CORE-R1 | **10.255.255.0/30** | **0** |

---

# ⚙️ Step-by-Step Configuration

## 🧱 Part A - Configure OSPF on HS-CORE-FW1

### 1️⃣ Enter OSPF process 1

In **global config mode**:

```bash
router ospf 1
```

### 2️⃣ Configure the router-id

```bash
router-id 10.0.0.20
```

### 3️⃣ Enable OSPF for the network 10.255.255.0/30 network:

```bash
network 10.255.255.0 255.255.255.252 area 0
```

#### ✅ This enables OSPF only for the **10.255.255.0/30** internal link (NOT the ISP link).

---

## 🧱 Part B - Configure OSPF on HS-CORE-R1

### 4️⃣ Enter OSPF process 1

#### 🔷 In global config mode

```bash
router ospf 1
```


### 5️⃣ Enable OSPF for the network 10.255.255.0/30 network (wildcard mask version)

```bash
network 10.255.255.0 0.0.0.3 area 0
```

