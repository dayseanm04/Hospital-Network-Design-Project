# 🌐 03 – Update NAT ACL to Exclude Printer IP Addresses

## 📌 Overview

Earlier, the **Translate-NAT** ACL I configured permitted entire /24 network for NAT translation.  
This means that printers IP addresses to be translated by NAT.

In this task  I will:
- Exclude printer IP addresses from NAT translation
- Apply updates on both edge routers (HS-EDGE-R1 & HS-EDGE-R2)



PAT allows multiple internal hosts to share a limited number of public IP addresses.

## Reference Topology

<img width="784" height="639" alt="topology" src="https://github.com/user-attachments/assets/5e8733fb-7ee1-4ac0-b0b5-9877d5e5b8fc" />


