# ⏱️ Test Distribution Switches NTP Synchronization

## 📌 Overview
This test verifies that **all distribution switches** in the Hospital Network Design project are **successfully synchronized with the internal NTP server**.

The goal is to confirm that **NTP configuration and authentication** are working correctly at the **distribution layer**, ensuring consistent time across the network core and access layers.

---

## 🎯 Test Objective

Confirm that:
- Distribution switches are synchronized with the NTP server
- The correct NTP server is being used
- NTP associations are established successfully

---

## 🏥 NTP Reference Information

| Item | Value |
|----|----|
| NTP Server IP | 10.10.10.3 |
| Expected Status | Clock synchronized |
| Verification Commands | `show ntp status`, `show ntp associations` |

---

## 🧪 Verification Steps  
Perform the following steps on **ALL distribution switches**:

### 1️⃣ Enter privileged EXEC mode

```bash
enable
```

### 🔶 DSW1

<img width="799" height="391" alt="DSW1" src="https://github.com/user-attachments/assets/c7aab103-15fb-4054-98c5-263bd01b8d41" />

### 🔶 DSW2

<img width="788" height="371" alt="DSW2" src="https://github.com/user-attachments/assets/b05418de-62ea-4323-939b-85ccacd461ba" />
