# 🔄 Change Log

## Reference Topology

<img width="483" height="313" alt="topology" src="https://github.com/user-attachments/assets/c2fcefc9-f2d9-4b7b-95aa-296558531494" />

## 🗓 Date

January 22 2026

## 📍 Layer
Core / Security

## 🖥 Devices Affected

- HS-CORE-R1 (Router → Layer 3 Switch)
- HS-CORE-FW1
- DSW1
- DSW2

## ⚙️ Change Type

- Device Replacement
- Layer 3 EtherChannel
- Core Uplink Redundancy

## 📝 Description

When I started this hospital network design project the Hospital I used a **single routed link** between **HS-CORE-R1** and **HS-CORE-FW1**.  
If that link failed, the **entire hospital LAN would lose connectivity**, creating a single point of failure.

To improve availability, I added an additional connection to the firewall.  
However, due to **Cisco Packet Tracer limitations**, I couldnt configured **Layer 3 EtherChannel** on the router (Cisco Packet Tracer Limitation).

To support a **redundant Layer 3 Port-Channel**, **HS-CORE-R1 was replaced with a Layer 3 switch**.  
I configured **static L3 EtherChannel (Port-channel 1)** between **HS-CORE-R1 and HS-CORE-FW1**, providing redundancy and higher bandwidth at the hospital core.










