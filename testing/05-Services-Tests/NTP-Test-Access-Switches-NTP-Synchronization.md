# ⏱️ Test Access Switches NTP Synchronization

## 📌 Overview
This test verifies that **all access switches** in the Hospital Network Design project are **successfully synchronized with the internal NTP server**.

The purpose of this test is to confirm that NTP configuration and authentication are working correctly at the **access layer**.

---

## 🎯 Test Objective

Confirm that:
- Access switches are synchronized with the NTP server
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
Perform the following steps on **ALL access switches**:

### 1️⃣ Enter privileged EXEC mode

```bash
enable
```

### ♦️ F1-ASW1

<img width="802" height="386" alt="F1-ASW1" src="https://github.com/user-attachments/assets/299ce9d8-96cc-4ea1-bf82-7c06b341a851" />

### ♦️ F1-ASW2

<img width="797" height="387" alt="F1-ASW2" src="https://github.com/user-attachments/assets/da033dec-9325-442a-b420-d874a56d89e1" />

### ♦️ F2-ASW1

<img width="801" height="391" alt="F2-ASW1" src="https://github.com/user-attachments/assets/d2b358ae-dd96-4d86-8aed-88781e944553" />

### ♦️ F2-ASW2

<img width="800" height="387" alt="F2-ASW2" src="https://github.com/user-attachments/assets/c407ef4f-b48e-490a-b01d-6d434548373e" />

### ♦️ F3-ASW1

<img width="794" height="389" alt="F3-ASW1" src="https://github.com/user-attachments/assets/2cc2fd67-7cd0-4733-a276-c3fc41227b63" />

### ♦️ F3-ASW2

<img width="791" height="390" alt="F3-ASW2" src="https://github.com/user-attachments/assets/82aa1380-117f-4dc7-9f59-828827068668" />

### ♦️ FService-ASW

<img width="783" height="431" alt="Service-ASW" src="https://github.com/user-attachments/assets/5cdd6f7f-ac2e-484d-bc7b-9c010755b7a4" />
