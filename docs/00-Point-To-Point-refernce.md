# 🔗 Point-to-Point Network Links (L3)

**Purpose:**  
This document tracks **all point-to-point (/30) Layer 3 links** in the hospital network design project.  

It includes:
- L3 EtherChannels P2P
- Edge Routers ↔ Core Firewall links
- Core Firewall  ↔ Distirubtion switches links

---

## 🧩 Section 1: Edge1 Router ↔ Edge2 Router Link

### 🟢 HS-EDGE-R1 to HS-EDGE-R2
| Link Name | Device A | Interface | IP Address | Device B | Interface | IP Address | Subnet (/30) |
|---|---|---|---|---|---|---|---|
| Edge to Edge | HS-EDGE-R1 | Po10 | 10.150.0.1 | HS-EDGE-R2 | Po10 | 10.150.255.2 | 10.150.0.0/30 |

## Reference Topology

<img width="431" height="155" alt="toplogy" src="https://github.com/user-attachments/assets/7bfab378-a78b-49a3-ba45-e9152faa611a" />


---

## 🧩 Section 2: Edge Routers ↔ Core Firewalls

### 🟢 HS-EDGE-R1 to HS-CORE-FW1 and HS-EDGE-R2 to HS-CORE-FW2

| Link Name | Device A | Interface | IP Address | Device B | Interface | IP Address | Subnet (/30) |
|---|---|---|---|---|---|---|---|
| Edge1 To Core1 | HS-EDGE-R1 | Po1 | 10.200.0.1 | DSW1 | Po1 | 10.200.0.2 | 10.200.0.0/30 |
| Edge2 To Core2 | HS-EDGE-R2 | Po1 | 10.200.0.5 | DSW1 | Po1 | 10.200.0.6 | 10.200.0.4/30 |

## Reference Topology

<img width="547" height="245" alt="toplogy" src="https://github.com/user-attachments/assets/59067c7d-58de-4f9d-a959-04331b553016" />

---

## 🧩 Section 3: Core Firewalls ↔ Distribution Switches

### 🟢  HS-CORE-FW1 to DSW1 and HS-CORE-FW2 to DSW2

| Link Name | Device A | Interface | IP Address | Device B | Interface | IP Address | Subnet (/30) |
|---|---|---|---|---|---|---|---|
| Core1 to DSW1 | HS-CORE-FW1 | Po20 | 10.255.0.1 | DSW1 | Po20 | 10.255.0.2 | 10.255.0.0/30 |
| Core2 To Core2 | HS-CORE-FW2 | Po20 | 10.255.0.5 | DSW1 | Po20| 10.255.0.6 | 10.255.0.4/30 |

## Reference Topology

<img width="545" height="221" alt="toplogy" src="https://github.com/user-attachments/assets/538b5146-9785-423d-ad3c-9fc3b3942294" />

---

## 🧩 Section 4: L3 EtherChannels (DSWs ↔ ASWs)

### 🟢 DSW ↔ Access Switch L3 EtherChannels
| Link Name | Device A | Port-Channel | IP Address | Device B | Port-Channel | IP Address | Subnet (/30) |
|---|---|---|---|---|---|---|---|
| DSW1 Po1 to F1-ASW1 Po1 | DSW1 | Po1  | 10.10.0.1 | F1-ASW1 | Po1 | 10.10.0.2  | 10.10.0.0/30 |
| DSW2 Po1 to F1-ASW1 Po2 | DSW2 | Po1  | 10.20.0.1 | F1-ASW1 | Po2 | 10.20.0.2  | 10.20.0.0/30 |
| DSW1 Po2 to F1-ASW2 Po1 | DSW1 | Po2  | 10.10.0.5 | F1-ASW2 | Po1 | 10.10.0.6  | 10.10.0.4/30 |
| DSW2 Po2 to F1-ASW2 Po2 | DSW2 | Po2  | 10.20.0.5 | F1-ASW2 | Po2 | 10.20.0.6  | 10.20.0.4/30 |
| DSW1 Po3 to F2-ASW1 Po1 | DSW1 | Po3  | 10.10.0.9 | F2-ASW1 | Po1 | 10.10.0.10  | 10.10.0.8/30 |
| DSW2 Po3 to F2-ASW1 Po2 | DSW2 | Po3  | 10.20.0.9 | F2-ASW1 | Po2 | 10.20.0.10  | 10.20.0.8/30 |
| DSW1 Po4 to F2-ASW2 Po1 | DSW1 | Po4  | 10.10.0.13 | F2-ASW2 | Po1 | 10.10.0.14  | 10.10.0.12/30 |
| DSW2 Po4 to F2-ASW2 Po2 | DSW2 | Po4  | 10.20.0.13 | F2-ASW2 | Po2 | 10.20.0.14  | 10.20.0.12/30 |
| DSW1 Po5 to F3-ASW1 Po1 | DSW1 | Po5  | 10.10.0.17 | F3-ASW1 | Po1 | 10.10.0.18  | 10.10.0.16/30 |
| DSW2 Po5 to F3-ASW1 Po2 | DSW2 | Po5  | 10.20.0.17 | F3-ASW1 | Po2 | 10.20.0.18  | 10.20.0.16/30 |
| DSW1 Po6 to F3-ASW2 Po1 | DSW1 | Po6  | 10.10.0.21 | F3-ASW2 | Po1 | 10.10.0.22  | 10.10.0.20/30 |
| DSW2 Po6 to F3-ASW2 Po2 | DSW2 | Po6  | 10.20.0.21 | F3-ASW2 | Po2 | 10.20.0.22  | 10.20.0.20/30 |

## Reference Topology

<img width="1107" height="358" alt="toplogy" src="https://github.com/user-attachments/assets/a611a419-9f27-4b99-827e-42010bc44519" />

---

## 🧩 Section 5: Service Switch Point-to-Point Links

### 🟢 Service-ASW ↔ DSWs (L3 EtherChannels)
| Link Name | Device A | Port-Channel | IP Address | Device B | Port-Channel | IP Address | Subnet (/30) |
|---|---|---|---|---|---|---|---|
| DSW1 to Service-ASW | DSW1 | Po7 | 10.255.2.1 | Service-ASW | Po1 | 10.255.2.1 | 10.255.2.0/30 |
| DSW2 to Service-ASW | DSW2 | Po7 | 10.255.2.5 | Service-ASW | Po2 | 10.255.2.6 | 10.255.2.4/30 |

---

## 🧩 Section 6: Edge Routers to ISP Point-to-Point Links

### 🔵 HS-EDGE-R1 to ISP1-R1 and HS-EDGE-R2 to ISP2-R1 

| Link Name | Device A | Port-Channel | IP Address | Device B | Port-Channel | IP Address | Subnet (/30) |
|---|---|---|---|---|---|---|---|
| Edge1 to ISP1 | HS-EDGE-R1 | Po15 | 69.45.12.1 | ISP1-R1 | Po15 | 69.45.12.2 | 69.45.12.0/30 |
| Edge2 to ISP2 | HS-EDGE-R2 | Po15 | 100.45.12.1 | ISP2-R1 | Po15 | 100.45.12.2 | 100.45.12.0/30 |


## 🧩 Section 7: ISP side Point-to-Point Links

| Link Name | Device A | Port-Channel | IP Address | Device B | Port-Channel | IP Address | Subnet (/30) |
|---|---|---|---|---|---|---|---|
| ISP2 to ISP1 | ISP2-R1 | Po15 | 10.50.50.1 | ISP1-R1 | Po15 | 10.50.50.2 | 10.50.50.0/30 |
| ISP1 to INET | ISP1-R1 | Po1 | 10.30.30.1 | INET-SW | Po1 | 10.30.30.2 | 10.30.30.0/30 |

## Reference Topology

<img width="587" height="524" alt="toplogy" src="https://github.com/user-attachments/assets/155a435e-076d-4644-a7dc-61f86a415f06" />




