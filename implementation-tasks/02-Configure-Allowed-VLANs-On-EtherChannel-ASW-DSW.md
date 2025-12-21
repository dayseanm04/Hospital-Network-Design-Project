# 🔀 02 – Configure Allowed VLANs on EtherChannel (ASW–DSW Links)

In this task I will configure **allowed VLANs on each EtherChannel trunk**
between **Access Switches (ASWs)** and **Distribution Switches (DSWs)**.

## Reference Diagram:

<img width="599" height="389" alt="implement-LACP" src="https://github.com/user-attachments/assets/314cc5bf-3f06-4b6c-bcfc-d408dab6711f" />

Only VLANs that are actually used on each access switch are allowed on the corresponding **Port-Channel interfaces**.

📌 Configuration approach:
- Enter global configuration mode on the switches
- Select the correct **Port-Channel interface**
- Configure the allowed VLAN list on the EtherChannel trunk

---

## 🏥 Floor 1 – EtherChannel Allowed VLANs

### 🔗 F1-ASW1 ↔ DSW1 / DSW2

| Device | Port-Channel | Connected To | Allowed VLANs |
|------|--------------|--------------|---------------|
| F1-ASW1 | Po1 | DSW1 Po1 | 101, 110, 600 |
| F1-ASW1 | Po2 | DSW2 Po1 | 101, 110, 600 |
| DSW1 | Po1 | F1-ASW1 Po1 | 1, 101, 110, 600 |
| DSW2 | Po1 | F1-ASW1 Po2 | 1, 101, 110, 600 |

### Verify F1-ASW1 show interface trunk

<img width="705" height="164" alt="F1-ASW1-trunk" src="https://github.com/user-attachments/assets/5f3eaa5e-212e-44c8-a53d-b9870d5f9190" />


### 🔗 F1-ASW2 ↔ DSW1 / DSW2

| Device | Port-Channel | Connected To | Allowed VLANs |
|------|--------------|--------------|---------------|
| F1-ASW2 | Po1 | DSW1 Po2 | 101, 120, 140, 180, 500 |
| F1-ASW2 | Po2 | DSW2 Po2 | 101, 120, 140, 180, 500 |
| DSW1 | Po2 | F1-ASW2 Po1 | 101, 120, 140, 180, 500 |
| DSW2 | Po2 | F1-ASW2 Po2 | 101, 120, 140, 180, 500 |


### Verify F1-ASW2 show interface trunk

<img width="670" height="163" alt="F1-ASW2-trunk" src="https://github.com/user-attachments/assets/cb323d8e-c200-483f-a3b9-caf86c460dec" />

---

## 🏢 Floor 2 – EtherChannel Allowed VLANs

### 🔗 F2-ASW1 ↔ DSW1 / DSW2

| Device | Port-Channel | Connected To | Allowed VLANs |
|------|--------------|--------------|---------------|
| F2-ASW1 | Po1 | DSW1 Po3 | 200, 210, 220, 500 |
| F2-ASW1 | Po2 | DSW2 Po3 | 200, 210, 220, 500 |
| DSW1 | Po3 | F2-ASW1 Po1 | 200, 210, 220, 500 |
| DSW2 | Po3 | F2-ASW1 Po2 | 200, 210, 220, 500 |

### Verify F2-ASW1 show interface trunk

















