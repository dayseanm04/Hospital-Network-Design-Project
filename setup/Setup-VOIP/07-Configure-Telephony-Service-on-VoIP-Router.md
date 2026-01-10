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

## ☎️ Configure Cisco Telephony Service

#### Enter global configuration mode on the VoIP router and apply the following:

```bash
telephony-service
max-ephones 30
max-dn 30
ip source-address 10.0.0.13 port 2000
auto-reg-ephone
auto assign 1 to 30
create cnf-files
```

### 🧾 Command Explanation

| Command               | Purpose                                  |
| --------------------- | ---------------------------------------- |
| `max-ephones 30`      | Maximum number of IP phones              |
| `max-dn 30`           | Maximum directory numbers (extensions)   |
| `ip source-address`   | Source IP used by telephony-service      |
| `auto-reg-ephone`     | Enables automatic IP phone registration  |
| `auto assign 1 to 30` | Automatically assigns extensions         |
| `create cnf-files`    | Generates configuration files for phones |
