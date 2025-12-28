# 🔗 Configure Layer 3 EtherChannel for DSWs to ASWs

## 📌 Overview
In this task I will configure **Layer 3 EtherChannels** between the **Distribution Switches (DSW1 and DSW2)** and the **Access Switches (ASWs)**.

I removed the **Layer 2 port-channels** and replaced with **routed EtherChannels** using **LACP**.  
Each DSW–ASW connection uses a dedicated **point-to-point /30 network**, allowing the access layer.

This approach provides:
- Better scalability
- Faster convergence
- Simplified troubleshooting
- Reduced Layer 2 dependency

## Reference Diagram

<img width="539" height="341" alt="topology" src="https://github.com/user-attachments/assets/ec132bce-d3eb-40b6-b22b-b0d694a93232" />

