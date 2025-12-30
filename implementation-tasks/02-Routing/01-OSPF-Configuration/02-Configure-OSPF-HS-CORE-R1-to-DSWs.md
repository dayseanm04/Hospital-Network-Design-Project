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

## 🟩 DSW1 (Enable OSPF on loopback + HS-CORE-R1 link)

### 3️⃣ Enter OSPF process 1

```bash
router ospf 1
```

### 4️⃣ Enable OSPF on the DSW1 loopback interface

```bash
network 10.0.0.10 0.0.0.0 area 0
```

### 5️⃣ Enable OSPF on the HS-CORE-R1 ↔ DSW1 /30 link

```bash
network 10.255.0.0 0.0.0.3 area 0`
```

---

## 🟨 DSW2 (Enable OSPF on loopback + HS-CORE link)

### 6️⃣ Enter OSPF process 1

```bashrouter ospf 1
```

### 7️⃣ Enable OSPF on the DSW2 loopback interface

```bash
network 10.0.0.11 0.0.0.0 area 0
```

### 8️⃣ Enable OSPF on the HS-CORE-R1 ↔ DSW2 /30 link

```bash 
network 10.255.0.4 0.0.0.3 area 0`
```

---


## 🔍 Verification (Run on HS-CORE-R1 + DSWs)

### 9️⃣ Confirm neighbors formed (the most important check)

#### show ip ospf neighbor on HS-CORE-R1

<img width="863" height="152" alt="HS-CORE-R1-ospf-neighbor" src="https://github.com/user-attachments/assets/8d193c14-3597-4087-936a-4e770d6fa78e" />

**Note 📢**: 
- 10.0.0.20 is HS-CORE-FW1 OSPF Router-ID
- 10.0.0.10 is DSW1 Loopback interface
- 10.0.0.11 is DSW2 Loopback interface

R1 successfully formed neighbors with DSW1 anbd DSW2


