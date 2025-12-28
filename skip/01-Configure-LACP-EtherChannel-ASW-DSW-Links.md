# 🔗 01 – Configure LACP EtherChannel on Access to Distribution Switches Links

---

## ❌Skip this step❌ and complete the following instead:  [Configure Layer 3 EtherChannel for DSWs to Service Switch (ASW ↔ DSW Links)](/implementation-tasks/01-Redundancy/02-Configure-L3-LACP-Etherchannel-Between-DSWs-To-ASWs.md)


---

In this task I will configure **LACP EtherChannel** between the
**Access Switches (ASWs)** and **Distribution Switches (DSWs)**.

## Reference Diagram:

<img width="599" height="389" alt="implement-LACP" src="https://github.com/user-attachments/assets/314cc5bf-3f06-4b6c-bcfc-d408dab6711f" />

EtherChannel is used to:
- Increase bandwidth
- Provide link redundancy
- Prevent STP from blocking parallel links

### 📌 Configuration approach:
- Enter global configuration mode on the switches
- Select the correct interface ranges
- Configure **LACP (mode active)**
- Assign interfaces to a Port-Channel
- Configure the Port-Channel as a trunk

---

## 🏥 Floor 1 – EtherChannel Links

### 🔗 F1-ASW1 ↔ DSW1

| Device | Interfaces | Port-Channel | LACP Mode | Description |
|------|------------|--------------|-----------|-------------|
| F1-ASW1 | Gi1/0/23–24 | Po1 | active | To-DSW1 |
| DSW1 | Gi1/0/1–2 | Po1 | active | To-F1-ASW1 |

---

### 🔗 F1-ASW1 ↔ DSW2

| Device | Interfaces | Port-Channel | LACP Mode | Description |
|------|------------|--------------|-----------|-------------|
| F1-ASW1 | Gi1/0/21–22 | Po2 | active | To-DSW2 |
| DSW2 | Gi1/0/1–2 | Po1 | active | To-F1-ASW1 

## F1-ASW1 show etherchannel summary

<img width="729" height="354" alt="F1-ASW1-LACP" src="https://github.com/user-attachments/assets/7d057be6-7012-480c-8367-c170dd881173" />

---

### 🔗 F1-ASW2 ↔ DSW1

| Device | Interfaces | Port-Channel | LACP Mode | Description |
|------|------------|--------------|-----------|-------------|
| F1-ASW2 | Gi1/0/23–24 | Po1 | active | To-DSW1 |
| DSW1 | Gi1/0/3–4 | Po2 | active | To-F1-ASW2 |

---

### 🔗 F1-ASW2 ↔ DSW2

| Device | Interfaces | Port-Channel | LACP Mode | Description |
|------|------------|--------------|-----------|-------------|
| F1-ASW2 | Gi1/0/21–22 | Po2 | active | To-DSW2 |
| DSW2 | Gi1/0/3–4 | Po2 | active | To-F1-ASW2 |

---

## F1-ASW2 show etherchannel summary

<img width="668" height="371" alt="F1-ASW2-LACP" src="https://github.com/user-attachments/assets/26475e4b-39fe-4b86-a050-d295a042a0dd" />

## 🏢 Floor 2 – EtherChannel Links

### 🔗 F2-ASW1 ↔ DSW1

| Device | Interfaces | Port-Channel | LACP Mode | Description |
|------|------------|--------------|-----------|-------------|
| F2-ASW1 | Gi1/0/23–24 | Po1 | active | To-DSW1 |
| DSW1 | Gi1/0/5–6 | Po3 | active | To-F2-ASW1 |

---

### 🔗 F2-ASW1 ↔ DSW2

| Device | Interfaces | Port-Channel | LACP Mode | Description |
|------|------------|--------------|-----------|-------------|
| F2-ASW1 | Gi1/0/21–22 | Po2 | active | To-DSW2 |
| DSW2 | Gi1/0/5–6 | Po3 | active | To-F2-ASW1 |

---

## F2-ASW1 show etherchannel summary

<img width="660" height="372" alt="F2-ASW1-LACP" src="https://github.com/user-attachments/assets/7fc05956-0f04-48c7-8716-c87c9761a033" />

---

### 🔗 F2-ASW2 ↔ DSW1

| Device | Interfaces | Port-Channel | LACP Mode | Description |
|------|------------|--------------|-----------|-------------|
| F2-ASW2 | Gi1/0/23–24 | Po1 | active | To-DSW1 |
| DSW1 | Gi1/0/7–8 | Po4 | active | To-F2-ASW2 |

---

### 🔗 F2-ASW2 ↔ DSW2

| Device | Interfaces | Port-Channel | LACP Mode | Description |
|------|------------|--------------|-----------|-------------|
| F2-ASW2 | Gi1/0/21–22 | Po2 | active | To-DSW2 |
| DSW2 | Gi1/0/7–8 | Po4 | active | To-F2-ASW2 |

---

## F2-ASW2 show etherchannel summary

<img width="647" height="373" alt="F2-ASW2-LACP" src="https://github.com/user-attachments/assets/f2d03db2-d32e-451c-94d6-ae24fdc891f1" />

---

## 🏨 Floor 3 – EtherChannel Links

### 🔗 F3-ASW1 ↔ DSW1

| Device | Interfaces | Port-Channel | LACP Mode | Description |
|------|------------|--------------|-----------|-------------|
| F3-ASW1 | Gi1/0/23–24 | Po1 | active | To-DSW1 |
| DSW1 | Gi1/0/9–10 | Po5 | active | To-F3-ASW1 |

---

### 🔗 F3-ASW1 ↔ DSW2

| Device | Interfaces | Port-Channel | LACP Mode | Description |
|------|------------|--------------|-----------|-------------|
| F3-ASW1 | Gi1/0/21–22 | Po2 | active | To-DSW2 |
| DSW2 | Gi1/0/9–10 | Po5 | active | To-F3-ASW1 |

---

## F3-ASW1 show etherchannel summary

<img width="623" height="372" alt="F3-ASW1-LACP" src="https://github.com/user-attachments/assets/576506ef-d939-4f87-84a3-8bb0e5a0319d" />

---

### 🔗 F3-ASW2 ↔ DSW1

| Device | Interfaces | Port-Channel | LACP Mode | Description |
|------|------------|--------------|-----------|-------------|
| F3-ASW2 | Gi1/0/23–24 | Po1 | active | To-DSW1 |
| DSW1 | Gi1/0/11–12 | Po6 | active | To-F3-ASW2 |

---

### 🔗 F3-ASW2 ↔ DSW2

| Device | Interfaces | Port-Channel | LACP Mode | Description |
|------|------------|--------------|-----------|-------------|
| F3-ASW2 | Gi1/0/21–22 | Po2 | active | To-DSW2 |
| DSW2 | Gi1/0/11–12 | Po6 | active | To-F3-ASW2 |



## F3-ASW2 show etherchannel summary

<img width="632" height="375" alt="F3-ASW2-LACP" src="https://github.com/user-attachments/assets/d4d61c9f-eedb-4806-8708-4f282c8913f6" />

### DSW1 show etherchannel summary

<img width="686" height="443" alt="DSW1-LACP" src="https://github.com/user-attachments/assets/d30c04d9-f91d-4063-9266-cd0006f4725f" />

### DSW2 show etherchannel summary

<img width="678" height="441" alt="DSW2-LACP" src="https://github.com/user-attachments/assets/1c71d8bb-3f43-4120-98a0-acf34f23e9b3" />


I confgiured LACP etherchannel for the access-distribution switches

<img width="610" height="397" alt="Screenshot 2025-12-20 234024" src="https://github.com/user-attachments/assets/d4bcbba3-8321-4fcf-82cd-6de9a0dced40" />
