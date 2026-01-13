# 🧪 07 – Verify HSRP Gateways and DHCP Assignments

This task verifies that **HSRP** and **DHCP** are working together correctly across the network.  

Clients should receive:
- A valid **IP address** from DHCP  
- The correct **HSRP Virtual IP (VIP)** as their **default gateway**


## 🎯 Validation Goals

- ✅ Confirm DHCP is operational after HSRP configuration
- ✅ Verify clients receive the **HSRP VIP** as the default gateway
- ✅ Ensure consistency across **multiple VLANs and floors**

## Reference Network Diagram

<img width="824" height="486" alt="Reference" src="https://github.com/user-attachments/assets/26bfde52-214f-4332-9805-20dfa415f224" />


---

## 🧠 Testing Approach

There are about  **20+ PCs** in the topology. Insted on testing on allf the the PC's, I will verify on 1 PC1 per vlan.

This is sufficient to confirm:

- DHCP scope   
- HSRP Gateway assignment via DHCP  

---

