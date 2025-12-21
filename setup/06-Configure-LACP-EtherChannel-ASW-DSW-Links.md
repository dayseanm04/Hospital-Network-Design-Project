# 🔗 06 – Configure LACP EtherChannel on Access to Distribution Switches Links

In this task I will implement **LACP EtherChannel** between the
**Access Switches (ASWs)** and **Distribution Switches (DSWs)**.

EtherChannel is used to:
- Increase bandwidth
- Provide link redundancy
- Prevent STP from blocking parallel links

📌 Configuration approach:
- Enter global configuration mode on the switches
- Select the correct interface ranges
- Configure **LACP (mode active)**
- Assign interfaces to a Port-Channel
- Configure the Port-Channel as a trunk

