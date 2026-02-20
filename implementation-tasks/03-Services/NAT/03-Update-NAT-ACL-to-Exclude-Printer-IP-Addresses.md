# 🌐 03 – Update NAT ACL to Exclude Printer IP Addresses

## 📌 Overview

Earlier, the **Translate-NAT** ACL I configured permitted entire /24 network for NAT translation.  
This means that printers IP addresses to be translated by NAT.

In this task  I will:
- Exclude printer IP addresses from NAT translation
- Apply updates on both edge routers (HS-EDGE-R1 & HS-EDGE-R2)


