# 🔄 Configuration Change Log

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
