# 🌐 Configure OSPF Between ISP1 and ISP2 Routers

In this task, I will configure **OSPF** between **ISP1-R1** and **ISP2-R1** so both ISP routers can dynamically exchange routing information.  

**Note:** I used a private IP for ISP1 to ISP2 to make it simple. Im building this project based on I learn from my CCNA studies. No BGP routing!

## 🎯 Objectives

- ✅ Configure a loopback interface on ISP2-R1
- ✅ Enable OSPF process **10** on both ISP routers
- ✅ Advertise the **point-to-point link** between ISP1 and ISP2
- ✅ Verify OSPF neighbor adjacency

## Reference Topology

<img width="416" height="332" alt="topology " src="https://github.com/user-attachments/assets/de2bfd6c-08cc-43be-ab4b-e4fa5ed49180" />

## 🔗 OSPF-Enabled Networks

### 📡 Point-to-Point Link (ISP1-R1 ↔ ISP2)

| Network | Wildcard Mask | Area |
|---|---|---|
| 10.50.50.0 | 0.0.0.3 | Area 0 |

### 🖧 Loopback Network (ISP2-R1 Only)

| Network | Wildcard Mask | Area |
|---|---|---|
| 10.10.10.20 | 0.0.0.0 | Area 0 |

---

## ISP2-R1

### 🟢 Configure ISP2-R1 loopback interface
In global config mode:

```bash
interface loopback0
 ip address 10.10.10.20 255.255.255.255
```

### 🟢 Advertised the networks

```bash
router ospf 10
 network 10.10.10.20 0.0.0.0 area 0
 network 10.50.50.0 0.0.0.3 area 0
```

## ISP1-R1

### 🟢 Enable OSPF for the P2P link to ISP2-R1

```bash
router ospf 10
 network 10.50.50.0 0.0.0.3 area 0
```

## 🔍 Verification

### show ip ospf neighbor on ISP1-R1

<img width="847" height="122" alt="ISP1" src="https://github.com/user-attachments/assets/63f2be92-a203-4cae-ba99-74b47d9f2e14" />

### show ip ospf neighbor on ISP2-R1

<img width="855" height="117" alt="ISP2" src="https://github.com/user-attachments/assets/17b8592d-ee8b-44d5-a8c5-e111103af807" />

ISP1-R1 and ISP2-R1 are neighbors
