# 📞 Configure-Voice-DHCP-Pools-on-VoIP-Router

## 📌 Overview

In this task I will configure **DHCP pools for all Voice VLANs** on the **VoIP Router**.  

The DHCP service assigns IP addresses to **IP phones** and provides **Option 150**, which points phones to the **TFTP/Call Manager (telephony-service)**.

---

## 🧠 Key Notes

- **DHCP Server:** VoIP Router
- **Clients:** IP Phones (Voice VLANs)
- **Option 150:** Used by IP phones to locate the telephony-service
- **Telephony-Service IP:** `10.0.0.13` (VOIP Router Loopback)

---

