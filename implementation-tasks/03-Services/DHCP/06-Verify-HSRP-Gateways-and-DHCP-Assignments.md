# 07 – Verify HSRP Gateways and DHCP Assignments

This task verifies that **HSRP** and **DHCP** are working together correctly across the network.  

Clients should receive:
- A valid **IP address** from DHCP  
- The correct **HSRP Virtual IP (VIP)** as their **default gateway**


## Validation Goals

- ✅ Confirm DHCP is operational after HSRP configuration
- ✅ Verify clients receive the **HSRP VIP** as the default gateway
- ✅ Ensure consistency across **multiple VLANs and floors**

## Reference Network Diagram

<img width="824" height="486" alt="Reference" src="https://github.com/user-attachments/assets/26bfde52-214f-4332-9805-20dfa415f224" />

---

## Testing Approach

There are about  **20+ PCs** in the topology. Insted on testing on allf the the PC's, I will verify on 1 PC1 per vlan.

This is sufficient to confirm:

- DHCP scope   
- HSRP Gateway assignment via DHCP  

---

## Test Method (Client Side)

#### 🟢 On ED-PC1 ipconfig /renew

<img width="610" height="320" alt="ED1-dhcp" src="https://github.com/user-attachments/assets/cb11fd94-7618-4374-9763-f152b2ba902e" />

Note: the first ipconfig /renew failed probabbly because packet tracer is slow, the second time it worked

#### 🟢 On XR-PC1 ipconfig /renew

<img width="628" height="281" alt="XR1-dhcp" src="https://github.com/user-attachments/assets/261265fd-544f-4885-aafa-25af4831b9fa" />

#### 🟢 On Nrs-PC1 ipconfig /renew

<img width="575" height="273" alt="NRs-PC1-dhcp" src="https://github.com/user-attachments/assets/1dbf35ac-80d5-464a-a11b-93222938012c" />

#### 🟢 On MRD-PC1 ipconfig /renew

<img width="592" height="264" alt="MRD-PC1" src="https://github.com/user-attachments/assets/c927282f-930b-432f-8db3-c9fbf9a13a82" />

#### 🟢 On Fin-PC1 ipconfig /renew

<img width="634" height="274" alt="Fin-PC1" src="https://github.com/user-attachments/assets/5bc91661-1661-45ef-b3fe-ee5b05af3df0" />

#### 🟢 On HR-PC1 ipconfig /renew

<img width="655" height="273" alt="HR-PC1" src="https://github.com/user-attachments/assets/f3c45622-64eb-42b6-8be8-e3b552920607" />

#### 🟢 On F3-Nrs-PC1 ipconfig /renew

<img width="641" height="275" alt="F3-Nrs-PC1" src="https://github.com/user-attachments/assets/00d458d4-9609-4e6f-a120-efb907393619" />

#### 🟢 On ICU-PC1 ipconfig /renew

<img width="592" height="274" alt="ICU-PC1" src="https://github.com/user-attachments/assets/da1d9164-df39-4da7-845c-ef19cc822dbd" />

#### 🟢 On Rad-PC1 ipconfig /renew

<img width="655" height="278" alt="Rad-PC1" src="https://github.com/user-attachments/assets/8880d1d5-199c-4284-b9d0-f2e26fb218ac" />

This validation confirms that: HSRP gateway redundancy is functioning correctly. DHCP scopes are properly aligned with HSRP VIPs.
