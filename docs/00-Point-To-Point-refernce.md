# 🔗 Point-to-Point Network Links (L3)

**Purpose:**  
This document tracks **all point-to-point (/30) Layer 3 links** in the hospital network design project.  

It includes:
- L3 EtherChannels (DSWs ↔ ASWs, DSWs ↔ DSWs)
- DSW ↔ Core Router links
- Core Router ↔ Firewall links

---

## 🧩 Section 1: Core Router ↔ Firewall Link

### 🔹 HS-CORE-FW1 ↔ HS-CORE-R1 
| Link Name | Device A | Interface | IP Address | Device B | Interface | IP Address | Subnet (/30) | OSPF Area |
|---|---|---|---|---|---|---|---|---|
| HS-CORE-FW1 to HS-CORE-R1 Link | HS-CORE-FW1 | G1/7 | 10.255.255.1/30 | HS-CORE-R1 | G0/0 | 10.255.255.2/30 | 10.255.255.0/30 | Area 0 |
