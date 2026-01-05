# 🧪 Test IT Department SSH Access to Network Device

## 📌 Purpose
This test verifies that **IT Department PCs** can successfully establish **SSH remote access** to a network device using **local user authentication**.

---

## 🖥️ Devices Used
| Device | Role |
|------|------|
| IT-PC1 | IT Department workstation |
| IT-PC2 | IT Department workstation |
| F1-ASW1 | Access Switch (SSH target) |

---

## 🔐 SSH Test Details
| Setting | Value |
|------|------|
| Protocol | SSH |
| Username | daysean |
| Password | ccna |
| Target Device | F1-ASW1 |
| Management IP (loopback) | 10.0.0.1 |

---

## 🧭 Test Steps

### 1️⃣ From **IT-PC1** and **IT-PC2**

1. Click **Desktop**
2. Open **Command Prompt**

---

### 2️⃣ SSH into the Network Device

Run the following command:
```bash
ssh -l daysean 10.0.0.1
```

<img width="679" height="253" alt="IT-DPT-SSH-access" src="https://github.com/user-attachments/assets/1c374b20-2b04-4419-8a98-7a769837c9ec" />


<img width="745" height="321" alt="IT-DPT-SSH-access2" src="https://github.com/user-attachments/assets/677c61e2-8255-4530-be82-13d4def0e570" />

IT-DPT PC1 and PC2 successfuly SSH into F1-ASW1
