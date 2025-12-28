# 🧭 01-Configure-OSPF-on-HS-CORE-FW1-and-HS-CORE-R1.md
**Goal:** Enable **OSPF Area 0 (backbone)** between **HS-CORE-FW1** and **HS-CORE-R1** over the **10.255.255.0/30** link. 

---

## 🗺️ Important Note
- **HS-CORE-FW1 G1/8** connects to **ISP1-R1**, so **do NOT run OSPF** on that interface/network.  
  - ISP link: **69.45.1.0/30** 

## Reference Network Diagram

<img width="534" height="258" alt="reference-network-digram" src="https://github.com/user-attachments/assets/29724aeb-e70a-4251-8dcf-6a96203ba71d" />

---
