# 🚨 Issue: Clients Not Receiving IP Due to Routing Issue (VLAN 101)

## 📌 Problem Description
**ED1 (Emergency DPT PC)** connected to **F1-ASW1** could not obtain an IP address from the **DHCP-SRV**, even after configuring an **IP helper address** on **VLAN 101**.

---

## 🌐 Affected Devices
- ED1 (Emergency DPT PC1)
- F1-ASW1
- DSW1 / DSW2
- Service-ASW
- DHCP-SRV

---

## ❌ Symptoms Observed
- ED1 could not receive an IP address from DHCP (DHCP request fails **See Below**).

<img width="600" height="204" alt="ED1-DHCP-Failed" src="https://github.com/user-attachments/assets/a0e89389-4189-4af8-a1d7-1de8c1bc05fb" />

- VLAN 101 details confirmed:
  - ED1 is in **VLAN 101**
  - VLAN 101 SVI is **172.16.1.1 /26**

---


## 🔍 Troubleshooting Steps Taken
1️⃣ **Verified DHCP-SRV IP settings**
- Checked DHCP-SRV IP, subnet, and default gateway → **Correct**

<img width="745" height="338" alt="DHCP-SRV-IP" src="https://github.com/user-attachments/assets/bc43b44e-15b1-4703-bf41-688c9707f51d" />

<img width="515" height="116" alt="SVI-IP" src="https://github.com/user-attachments/assets/e375aed1-a1aa-492f-8b6f-3585fe1aebae" />


