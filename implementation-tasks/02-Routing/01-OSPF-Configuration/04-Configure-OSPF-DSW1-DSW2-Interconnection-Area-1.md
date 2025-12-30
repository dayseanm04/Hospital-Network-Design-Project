# 🌐 Configure-OSPF-For-DSW1-DSW2-Interconnection.md  

**Goal:** Enable OSPF on the **DSW1 ↔ DSW2 interconnection Area 0 (Backbone)**.

## Reference Network Diagram

<img width="555" height="373" alt="reference-net-diagram" src="https://github.com/user-attachments/assets/39b1e53f-8042-466b-a632-bd755b20b41e" />

---

# 🛠️ Configure DSW1

## 1️⃣ On **DSW1** - Enable OSPF on the interconnect (/30)

#### ♦️ Go to global config, then config OSPF, and add the network statement:

```bash
router ospf 1
network 10.255.1.0 0.0.0.3 area 0
```

**✅ This enables OSPF on the portchannel to DSW1.**

---
