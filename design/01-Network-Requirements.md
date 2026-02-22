# 01 – Network Requirements

Because hospitals rely on access to medical systems, patient records, and communication tools, the network must be **fast, secure, redundant, and highly available** at all times.

---

##  1. High Availability

The hospital network must remain available 24/7.  
Requirements include:

- Redundant switches and routers  
- Failover paths for critical departments (ED, ICU, Imaging)  

High availability ensures that patient care systems and hospital applications stay online.

---

##  2. Redundancy

Redundancy protects the network against hardware or link failures.  
The design must include:

- Redundant links 
- Backup routing paths  

If one device or link goes down, traffic should automatically reroute.

---

## 3. Network Segmentation (VLANs)

To improve performance and security, the network must separate traffic by department or function:

- Emergency Department  
- Administration / Billing  
- ICU & Inpatient Care  
- Imaging / Radiology  
- Pharmacy  

Segmentation helps reduce congestion and limits security risks.

---

## 📌  Security Requirements

Security is critical to protect patient information and hospital systems.  
Requirements include:

- ACLs to restrict access between departments  
- Firewall  
- Protection for sensitive medical devices  

--- 

## 5. Scalability

The network must support future expansion, including:

- Additional patient rooms  
- New departments or clinics  
- More PCs, phones, printers, and medical devices  
- Additional servers or cloud services  

The design should make upgrades easy without major redesign.

---

### Note Since im using Cisco Packet Tracer there are some limitations
- The devices are strictly PCs, IP Phones and printers. It dosent include hospital equipments since I cant simulate that in Packet Tracer
