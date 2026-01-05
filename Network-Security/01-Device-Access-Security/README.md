# 🔐 Device Access Security

This folder contains step by step configurations used to **secure access to network devices** in the hospital network project.  
The goal is to protect the **management plane** by controlling how administrators access routers and switches.

---

## 🎯 Objectives

- Require **local username and password authentication**
- Protect **privileged EXEC mode** with an enable secret
- Secure **console and remote access** to devices
- Reduce the risk of **unauthorized access** to network infrastructure

---

## 📂 Contents

| File | Description |
|-----|------------|
| `01-configure-local-user-and-enable-secret.md` | Creates local user accounts and secures privileged mode |
| `02-secure-console-access-with-local-authentication.md` | Secures console access using local authentication and timeouts |

---

## 🛡️ Notes

- Credentials used in this project are **simplified for lab purposes**
- In a real production environment, **strong passwords and additional controls** would be required
- These configurations are applied consistently across devices for **standardization**
