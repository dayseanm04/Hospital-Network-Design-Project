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
router ospf 1
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
network 10.255.0.0 0.0.0.3 area 0
```

---

## 🟨 DSW2 (Enable OSPF on loopback + HS-CORE link)

### 6️⃣ Enter OSPF process 1

```bash
router ospf 1
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

HS-CORE-R1 successfully became with DSW1 anbd DSW2

#### show ip ospf neighbor on DSW1

<img width="881" height="256" alt="DSW1-ospf-neighbor" src="https://github.com/user-attachments/assets/bed84f66-f528-4b89-ace2-92ebfe1935a7" />

DSW1 successfully became with HS-CORE-R1

#### show ip ospf neighbor on DSW2

<img width="870" height="242" alt="DSW2-ospf-neighbor" src="https://github.com/user-attachments/assets/352ea4af-2e0c-41a7-a91d-4a4d49bf243a" />

DSW2 also successfully became with HS-CORE-R1

**Note 📢**: 
- 10.0.0.15 is HS-CORE-R1 OSPF loopback interface

---


### 🔟 Check OSPF is running + which networks are included

#### show ip protocol on HS-CORE-R1

<img width="635" height="226" alt="HS-CORE-R1-ospf-is-running" src="https://github.com/user-attachments/assets/594d259e-3e5d-4453-8749-1a85c41dffad" />

#### show ip protocol on DSW1

<img width="757" height="264" alt="DSW1-ospf-is-running" src="https://github.com/user-attachments/assets/9a5c4ee1-3af3-4f71-8ffc-e581d9e3b8c7" />

#### show ip protocol on DSW2

<img width="689" height="259" alt="DSW2-ospf-is-running" src="https://github.com/user-attachments/assets/958a7c36-1288-4487-b748-c391711fb3e7" />










