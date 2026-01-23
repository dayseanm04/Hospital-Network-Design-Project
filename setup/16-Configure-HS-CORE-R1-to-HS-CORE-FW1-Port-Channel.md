# 🔗 Configure HS-CORE-R1 to HS-CORE-FW1 Port-Channel

## 📌 Overview

In this task, I configure a **Layer 3 EtherChannel (static Port-Channel)** between the **HS-CORE-R1** and the **HS-CORE-FW1**.

This design removes the **single point of failure** created by a single uplink between the core and firewall.  

## 🎯 Goals
- Configure Port-Channel for the connection to HS-CORE-FW1
- Bundle them into **Port-channel 1**
- Assign routed /30 IP addressing for the Port-Channel
- Set the firewall Port-Channel as the **inside** interface
- Verify EtherChannel


## Reference Topology

<img width="483" height="313" alt="topology" src="https://github.com/user-attachments/assets/642f493d-b5b0-436e-b8d2-c4658b34ed3b" />

