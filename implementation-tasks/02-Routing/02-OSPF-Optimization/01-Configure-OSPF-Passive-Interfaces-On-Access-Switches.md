# 💤 Configure OSPF Passive Interfaces (OSPF Optimization)

## 📌 Overview
This task configures **OSPF passive interfaces for VLANs on the access switches** so that **OSPF routing updates are not sent or received on user VLANs**.

The VLAN networks remain advertised in OSPF, but **end devices do not participate in OSPF neighbor formation**, which improves security and reduces unnecessary routing traffic.

---

## 🎯 Objective

- Prevent OSPF hello packets on end-user VLANs
- Reduce OSPF overhead on the access layer

---

## 🧾 VLANs to Make Passive

| Access Switch | VLANs (Passive) |
|-------------|------------------|
| **F1-ASW1** | 101, 110 |
| **F1-ASW2** | 120 |
| **F2-ASW1** | 200, 220 |
| **F2-ASW2** | 210 |
| **F3-ASW1** | 300 |
| **F3-ASW2** | 310, 330 |

---

## ⚙️ Configuration Steps

### 1️⃣ Enter OSPF configuration mode
```bash
router ospf 1
```

### 2️⃣ Configure passive interfaces for the VLANs on that switch

```bash
passive-interface Vlan <VLAN-ID>
end
```

### 💾 Save Configuration

```bash
write memory
```













