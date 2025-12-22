# 🌐08 Configure IP for Distribution Switches to HS-CORE-R1.md

In this task I will configure **point-to-point IP addresses** between the **Distribution Switches (DSW1/DSW2)** and the **Hospital Core Router (HS-CORE-R1)**.

✅ These links are configured as **Layer 3 routed links** using **/30 networks**.  

## Reference Diagram

<img width="611" height="230" alt="reference-diagram" src="https://github.com/user-attachments/assets/6910949d-013f-4fe6-85b5-d498ad276e0a" />

---

## 🔗 Connections

| Link | Device A | Interface A | Device B | Interface B |
|------|----------|-------------|----------|-------------|
| Link 1 | DSW1 | Gi1/1/1 | HS-CORE-R1 | Gi2/0 |
| Link 2 | DSW2 | Gi1/1/1 | HS-CORE-R1 | Gi3/0 |

---

## 🧠 IP Addressing Plan (Point-to-Point /30)

| Link | Network (CIDR) | Subnet Mask | Usable IPs |
|------|-----------------|-------------|------------|
| HS-CORE-R1 ↔ DSW1 | 10.255.0.0/30 | 255.255.255.252 | 10.255.0.1 – 10.255.0.2 |
| HS-CORE-R1 ↔ DSW2 | 10.255.0.4/30 | 255.255.255.252 | 10.255.0.5 – 10.255.0.6 |

---

## 📌 Interface IP Assignments

### ✅ HS-CORE-R1 Interfaces

### ✅ HS-CORE-R1 Interfaces

| Device | Interface | Connected To | IP Address / Mask | Description |
|--------|-----------|--------------|-------------------|-------------|
| HS-CORE-R1 | Gi2/0 | DSW1 Gi1/1/1 | 10.255.0.1 /30 | to DSW1 |
| HS-CORE-R1 | Gi3/0 | DSW2 Gi1/1/1 | 10.255.0.5 /30 | to DSW2 |

---

### ✅ Distribution Switch Interfaces

| Device | Interface | Connected To | L3 Setting | IP Address / Mask | Description |
|--------|-----------|--------------|-----------|-------------------|-------------|
| DSW1 | Gi1/1/1 | HS-CORE-R1 Gi2/0 | `no switchport` | 10.255.0.2 /30 | to HS-CORE-R1 |
| DSW2 | Gi1/1/1 | HS-CORE-R1 Gi3/0 | `no switchport` | 10.255.0.6 /30 | to HS-CORE-R1 |

### 📌 Important:  

On the multilayer switches (DSW1&DSW2), use `no switchport` command so the interface becomes Layer 3.  

## ✅ Verification

### On HS-CORE-R1 show ip int brief 

<img width="826" height="121" alt="HS-CORE-R1-show-ip" src="https://github.com/user-attachments/assets/5ccc4c8b-0011-4bc5-a1e1-c212d3686feb" />

### On DSW1 show ip int brief | begin GigabitEthernet1/1/

<img width="784" height="121" alt="DSW1-show-ip" src="https://github.com/user-attachments/assets/303d9581-5fd4-42bb-b207-0b9f2f36c18b" />


### On DSW2 show ip int brief | begin GigabitEthernet1/1/

<img width="808" height="120" alt="DSW2-show-ip" src="https://github.com/user-attachments/assets/36c1106a-e2f4-4c45-8f56-f4a2a12405a1" />








