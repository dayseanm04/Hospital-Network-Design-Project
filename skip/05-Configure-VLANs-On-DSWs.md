# 🧩 05 – Configure VLANs on Distribution Switches (DSWs)

## 📢 SKIP THIS STEP

In this task I will configure VLANs on the **Distribution Switches (DSW1 and DSW2)**.

Because all Access Switches connect to the Distribution layer using **trunk links**,  
the Distribution Switches must have **all required VLANs created** so they can be carried across the trunks.

📌 In this task i will:
- Create VLANs on DSW1 and DSW2
- Name VLANs
- Ensure VLAN consistency across the distribution layer

---

## 🏛️ Distribution Switches

- **DSW1** – Cisco 3650-24PC  
- **DSW2** – Cisco 3650-24PC  

Both switches use the **same VLAN database**.

---

## 🏥 Floor 1 VLANs (Configured on DSW1 & DSW2)

| VLAN ID | VLAN Name |
|--------:|-----------|
| 101 | Emergency-DPT |
| 110 | X-Ray-Imaging-DPT |
| 120 | Nurse-Stations |
| 140 | Pharmacy |
| 180 | Supply-Chain-Purchasing |

---

## 🏢 Floor 2 VLANs (Configured on DSW1 & DSW2)

| VLAN ID | VLAN Name |
|--------:|-----------|
| 200 | Medical-Rec-DPT |
| 210 | Billing-Finance-DPT |
| 220 | HumanResources-DPT |
| 230 | Insurance-DPT |
| 240 | IT-DPT |

---

## 🏨 Floor 3 VLANs (Configured on DSW1 & DSW2)

| VLAN ID | VLAN Name |
|--------:|-----------|
| 300 | Nurse-Offices |
| 310 | ICU-DPT |
| 320 | Inpatient-DPT |
| 330 | Radiology-DPT |

---

## 🧍 Shared VLANs (All Floors)

These VLANs are used across multiple floors and must exist on **both distribution switches**.

| VLAN ID | VLAN Name | Purpose |
|--------:|-----------|---------|
| 500 | Security-Stations | Security offices and stations |
| 600 | Receptionists | Front desk and receptionist areas |

---
## 🔍 Verification (Run on DSW1 & DSW2)

### show vlan brief on DSW1

<img width="919" height="442" alt="DSW1-VLAN-verification" src="https://github.com/user-attachments/assets/72c8dee5-0b07-4102-97e1-42f2566fb67d" />

### show vlan brief on DSW2

<img width="920" height="438" alt="DSW2-VLAN-verification" src="https://github.com/user-attachments/assets/6b9018e8-98b5-4bbe-922e-9293d32feb85" />


## ✅ Summary

- All VLANs used on **Access Switches** are also created on **DSW1 and DSW2**
- This ensures VLAN traffic can traverse **trunk links** without issues
- VLAN naming is consistent across access and distribution layers
- No IP addressing or routing is configured in this task

---

📌 **Note:**  

I could have configured VLANs on the Distribution Switches using **VLAN Trunking Protocol (VTP)**.  
However, I **manually configured them** in this project to keep configuration **simple, predictable, and CCNA-level**, and to avoid unintended VLAN changes across the network.
