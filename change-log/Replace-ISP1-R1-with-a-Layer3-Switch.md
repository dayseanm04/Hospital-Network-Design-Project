# 🔄 Change Log

## 🗓 Date
January 20 2026

## 📍 Layer

ISP side

## 🖥 Devices Affected

- HS-CORE-FW1
- ISP1-R1 (to be removed)
- ISP1-L3-SW1 (Cisco 3650-24PS – replacement device)

## ⚙️ Change Type

Device change

## 📝 Description

When I started this hospital network design project the Hospital had 1 connection to ISP1. To improve link redundancy and bandwidth, I addeded another link. However, due to Cisco Packet Tracer limitations, I couldnt configure EtherChannel on the router.

To resolve this limitation, I replaced ISP1-R1 (router) with a Layer 3 switch (Cisco 3650-24PS). This change enables the use of Layer 3 EtherChannel between the hospital core firewall and the ISP edge device.

## 🎯 Reason

The ISP Router did not support EtherChannel (Cisco Packet Tracer) limitation.

## 🔗 Related Task / Design Doc
- [**Configure-INET-Services-Network-Behind-ISP1**](/skip/09-Configure-INET-Services-Network-Behind-ISP1.md)
- [**Build-Physical-and-Core-Connections**](/setup/01-Build-Physical-and-Core-Connections.md)


## ✅ Verification

## Reference Topology

<img width="566" height="231" alt="new-topology" src="https://github.com/user-attachments/assets/34d66c7d-3033-4257-a20e-9ba8fad5be5b" />

