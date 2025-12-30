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
| HS-CORE-FW1 HS-CORE-R1 | HS-CORE-FW1 | G1/7 | 10.255.255.1 | HS-CORE-R1 | G0/0 | 10.255.255.2 | 10.255.255.0/30 | Area 0 |

---

## 🧩 Section 2: Distribution Switch ↔ Core Router Links

### 🔹 DSW ↔ HS-CORE-R1
| Link Name | Device A | Interface | IP Address | Device B | Interface | IP Address | Subnet (/30) |
|---|---|---|---|---|---|---|---|
| DSW1 to HS-CORE-R1 | HS-CORE-R1 | G2/0  | 10.255.0.1 | DSW1 | G1/1/1 | 10.255.0.2 | 10.255.0.0/30 |
|  DSW2 to HS-CORE-R1 | HS-CORE-R1 | G3/0 | 10.255.0.5 | DSW2 | G1/1/1 | 10.255.0.6 | 10.255.0.4/30 |

---

## 🧩 Section 3: L3 EtherChannels (DSWs ↔ ASWs)

### 🔹 DSW ↔ Access Switch L3 EtherChannels
| Link Name | Device A | Port-Channel | IP Address | Device B | Port-Channel | IP Address | Subnet (/30) |
|---|---|---|---|---|---|---|---|
| DSW1 Po1 to F1-ASW1 Po1 | DSW1 | Po1  | 10.10.0.1 | F1-ASW1 | Po1 | 10.10.0.2  | 10.10.0.0/30 |
| DSW2 Po1 to F1-ASW1 Po2 | DSW2 | Po1  | 10.20.0.1 | F1-ASW1 | Po2 | 10.20.0.2  | 10.20.0.0/30 |
| DSW1 Po2 to F1-ASW2 Po1 | DSW1 | Po2  | 10.10.0.5 | F1-ASW2 | Po1 | 10.10.0.6  | 10.10.0.4/30 |
| DSW2 Po2 to F1-ASW2 Po2 | DSW2 | Po2  | 10.20.0.5 | F1-ASW2 | Po2 | 10.20.0.6  | 10.20.0.4/30 |
| DSW1 Po3 to F2-ASW1 Po1 | DSW1 | Po3  | 10.10.0.9 | F2-ASW1 | Po1 | 10.10.0.10  | 10.10.0.8/30 |
| DSW2 Po3 to F2-ASW1 Po2 | DSW2 | Po3  | 10.20.0.9 | F2-ASW1 | Po1 | 10.20.0.10  | 10.20.0.8/30 |
| DSW1 Po4 to F2-ASW2 Po1 | DSW1 | Po4  | 10.10.0.13 | F2-ASW2 | Po1 | 10.10.0.14  | 10.10.0.12/30 |

