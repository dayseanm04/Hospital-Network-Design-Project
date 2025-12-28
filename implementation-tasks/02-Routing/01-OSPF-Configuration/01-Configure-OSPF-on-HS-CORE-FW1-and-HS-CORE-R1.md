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

# ✅ Verification

### 6️⃣ Verify OSPF Neighbor Relationship

#### show ip ospf neighbor on HS-CORE-R1

<img width="861" height="102" alt="HS-CORE-R1-show-ospf-neighbor" src="https://github.com/user-attachments/assets/2755a8f6-f83d-4fba-8daf-12054ac7746f" />

**HS-CORE-R1 is neighbors with HS-CORE-FW1**

## 7️⃣ Verify OSPF is running and the network is included

#### show ip protocols on HS-CORE-R1

<img width="732" height="333" alt="HS-CORE-R1-show-ip-protocols" src="https://github.com/user-attachments/assets/a08e6256-5295-4b1e-b2bd-2e8e35c95945" />

### 8️⃣ show run | section router on HS-CORE-FW1

<img width="599" height="132" alt="HS-CORE-FW1-ospf" src="https://github.com/user-attachments/assets/5b0499e1-d6ae-4da6-8328-61f3de1bf6e2" />





