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

