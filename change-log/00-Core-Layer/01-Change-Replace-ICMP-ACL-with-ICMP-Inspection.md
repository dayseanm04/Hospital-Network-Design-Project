# 🔄 Configuration Change Log

## Reference Topology

<img width="968" height="310" alt="reference-topology" src="https://github.com/user-attachments/assets/87fc634c-6ce6-49ac-b1c1-fa64cdf7a90a" />

## 🗓 Date
January 17 2026

## 📍 Layer
Security (Core Firewall)

## 🖥 Devices Affected
- HS-CORE-FW1  
- HS-CORE-R1 (verification only)

## ⚙️ Configuration Type
Firewall / ICMP Inspection

## 📝 Description

Removed the temporary **ACL that explicitly permitted ICMP traffic** from **HS-CORE-R1 to HS-CORE-FW1** and replaced it with a **stateful ICMP inspection policy** on the firewall.  

I configured a global policy was on **HS-CORE-FW1** to inspect ICMP traffic using the default inspection class, allowing ICMP echo and reply traffic without relying on static ACL rules

## 🎯 Reason

I configured the ICMP ACL to test connectivty from HS-CORE-R1 to HS-CORE-FW1.  

Using **ICMP inspection** is a more scalable and secure solution, as it dynamically allows return ICMP traffic to return back to the firewall.

## 🔗 Related Task 

- [Issue-HS-CORE-R1-To-HS-CORE-FW1-Ping-Failure.md](/troubleshooting/01-Connectivity-Issues/Issue-HS-CORE-R1-To-HS-CORE-FW1-Ping-Failure.md)

## ✅ Verification

<img width="910" height="278" alt="HS-R-to-HS-FW" src="https://github.com/user-attachments/assets/68e674c9-b3b6-4f17-aabf-4c50bdefd3de" />

- I ping from **HS-CORE-R1** to **HS-CORE-FW1** (successful)
- ICMP echo requests and replies verified after ACL removal


