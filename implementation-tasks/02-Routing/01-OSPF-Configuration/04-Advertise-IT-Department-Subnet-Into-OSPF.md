# 🌐 Enable OSPF for the IT DPT Subnet (10.50.50.0/26)

I this task I will advertise the **IT Department subnet (10.50.50.0/26)** into **OSPF Process 1 (Area 1)** so it is reachable throughout the network.


## 🧩 IT DPT Subnet Info

| VLAN/Dept | Subnet | Wildcard | OSPF Area |
|---|---|---|---|
| IT Department | 10.50.50.0/26 | 0.0.0.63 | Area 10 |

## Reference Network Diagram

<img width="440" height="196" alt="reference-net-diagram" src="https://github.com/user-attachments/assets/a61dcd37-29b7-4bc2-8ed0-72016796c3d2" />

---

## ✅ Step 1 - Configure OSPF on **Service-ASW** 🖥️

### 1️⃣Enter Global Config mode:

```bash
enable
configure terminal
```

### 2️⃣ Enter OSPF process 1:

```bash
router ospf 10
```

### 3️⃣ Advertise the IT subnet into Area 1:

```bash
network 10.50.50.0 0.0.0.63 area 1
```

## 🔍 Step 2 - Verify on Service-ASW ✅

```bash
show ip protocols
```

<img width="745" height="264" alt="verify-ospf-IT-dpt-subnet" src="https://github.com/user-attachments/assets/26c9fc4b-755e-4354-aea0-1755d34187ae" />

## 🔍 Step 3 - Verify on DSW1 and DSW2 ✅

```bash
show ip route | include 10.50.50.0
```

<img width="782" height="84" alt="verify-ospf-IT-dpt-subnet-DSW1" src="https://github.com/user-attachments/assets/0a140edc-82e4-4e57-9fd7-47cb91aef8e5" />

<img width="733" height="63" alt="verify-ospf-IT-dpt-subnet-DSW2" src="https://github.com/user-attachments/assets/f0b85cc6-6a6d-4ce7-8e38-df2d33535abc" />


#### ✅ DSW1 and DSW2 successfully learned the route to the IT DPT subnet (10.50.50.0/26)

Note: I changed the process ID  to 10
