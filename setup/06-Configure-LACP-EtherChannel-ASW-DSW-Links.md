# 🔗 06 – Configure LACP EtherChannel on Access to Distribution Switches Links

In this task I will implement **LACP EtherChannel** between the
**Access Switches (ASWs)** and **Distribution Switches (DSWs)**.

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

