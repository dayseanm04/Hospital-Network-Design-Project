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




