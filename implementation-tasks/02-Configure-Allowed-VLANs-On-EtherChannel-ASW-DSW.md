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

