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
| **Service-ASW1** | 240, 700 |

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

## ✅ Verification (Run on ALL Access Switches)

#### 🔷 show ip protocols on F1-ASW1

<img width="770" height="316" alt="F1-ASW1" src="https://github.com/user-attachments/assets/7c06e4bf-80f4-4d15-a867-d4c29fc4cef8" />

#### 🔷 show ip protocols on F1-ASW2

<img width="680" height="299" alt="F1-ASW2" src="https://github.com/user-attachments/assets/b9e2f0b2-e658-4b7e-86d1-f85bace0edb4" />

#### 🔷 show ip protocols on F2-ASW1

<img width="797" height="322" alt="F2-ASW1" src="https://github.com/user-attachments/assets/bbc134a0-8c20-4b6c-b338-a198d968996a" />

#### 🔷 show ip protocols on F2-ASW2

<img width="773" height="278" alt="F2-ASW2" src="https://github.com/user-attachments/assets/4132c329-873f-4e95-96db-47bc03c3649f" />

#### 🔷 show ip protocols on F3-ASW1

<img width="795" height="284" alt="F3-ASW1" src="https://github.com/user-attachments/assets/b5e62199-eeb6-4bb7-9aa0-1716ea3c0a0a" />

#### 🔷 show ip protocols on F3-ASW2

<img width="746" height="334" alt="F3-ASW2" src="https://github.com/user-attachments/assets/11965dfe-5afc-4751-a91d-a305bbe1b7ef" />

#### 🔷 show ip protocols on Service-ASW

<img width="746" height="334" alt="F3-ASW2" src="https://github.com/user-attachments/assets/4414a49f-5f50-42bb-9f12-f3bf7f759e1e" />






