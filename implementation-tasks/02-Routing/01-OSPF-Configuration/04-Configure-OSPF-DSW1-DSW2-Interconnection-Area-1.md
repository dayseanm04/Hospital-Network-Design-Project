# 🌐 Configure-OSPF-For-DSW1-DSW2-Interconnection.md  

**Goal:** Enable OSPF on the **DSW1 ↔ DSW2 interconnection Area 0 (Backbone)**.

## Reference Network Diagram

<img width="555" height="373" alt="reference-net-diagram" src="https://github.com/user-attachments/assets/39b1e53f-8042-466b-a632-bd755b20b41e" />

---

# 🛠️ Configure Distribution Switches

## 1️⃣ On **DSW1** - Enable OSPF on the interconnect (/30)

#### ♦️ Go to global config, then config OSPF, and add the network statement:

```bash
router ospf 1
network 10.255.1.0 0.0.0.3 area 0
```

**✅ This enables OSPF on the portchannel to DSW1.**

---

## 2️⃣ On **DSW2** - Enable OSPF on the interconnect (/30)

#### ♦️ Go to global config, then config OSPF, and add the network statement:

```bash
router ospf 1
network 10.255.1.0 0.0.0.3 area 0
```

**✅ This enables OSPF on the portchannel to DSW1.**

---

# ✅ Verification

## 3️⃣ Confirm OSPF is advertising the interconnect on both switches

#### ♦️ show ip protocols on DSW1

<img width="658" height="266" alt="DSW1-show-ip-protocols" src="https://github.com/user-attachments/assets/81bfa6f8-a45b-4869-b6cf-2bbe743431d0" />

#### ♦️ show ip protocols on DSW2
<img width="645" height="262" alt="DSW2-show-ip-protocols" src="https://github.com/user-attachments/assets/61696f1c-fde9-476d-bfb4-77fe154870dc" />

**Note: Both Distrution switches is routing for the 10.255.1.0 0.0.0.3 network in area 0**
