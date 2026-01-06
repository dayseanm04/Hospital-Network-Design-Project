# ⏱️ Test Core Devices NTP Synchronization

## 📌 Overview
This test verifies that **core network devices** in the Hospital Network Design project are **successfully synchronized with the internal NTP server**.

Ensuring accurate time at the core layer is critical because core devices handle **routing, security events, and centralized logging**.

---

## 🎯 Test Objective

Confirm that:
- Core devices are synchronized with the internal NTP server
- The correct NTP server is being used
- NTP associations are established and stable

---

## 🏥 NTP Reference Information

| Item | Value |
|----|----|
| NTP Server IP | 10.10.10.3 |
| Expected Status | Clock synchronized |
| Verification Commands | `show ntp status`, `show ntp associations` |

---

## 🧪 Verification Steps  
Perform the following steps on **ALL core devices**:

### 1️⃣ Enter privileged EXEC mode

```bash
enable
```

### 🔶 HS-CORE-R1

<img width="802" height="387" alt="HS-CORE-R1" src="https://github.com/user-attachments/assets/f1563865-9875-43b3-8d0f-8063ec29cc96" />

