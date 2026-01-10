# 📞 Configure-Cisco-Telephony-Service-on-VoIP-Router

## 📌 Overview

In this task I will configure **Cisco telephony-service** on the **VoIP router**. 
Telephony-service allows the router to act as a **call control server**, enabling **IP phone registration, extension assignment, and call handling** in Packet Tracer.

I used the **loopback interface** as a source IP for VoIP services.

---

## 🧠 Key Notes

- **Router Role:** VoIP / Call Control Gateway  
- **IP Phones Used:** Limited due to Packet Tracer constraints  
- **Max Phones Configured:** 30  
- **Source Address:** Loopback interface

## Reference Network Diagram

<img width="796" height="371" alt="network-diagram" src="https://github.com/user-attachments/assets/4760b50a-76e8-452c-a214-d7eb81876b0f" />

---

## 🔁 Configure Loopback Interface

The loopback interface provides a **reliable IP address** for the telephony service.

```bash
interface loopback 0
ip address 10.0.0.13 255.255.255.255
```
