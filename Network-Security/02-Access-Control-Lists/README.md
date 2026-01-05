# 🔐 Access Control Lists (ACLs)

## 📌 Overview

This folder contains **Access Control List (ACL) configurations and references** used in the Hospital Network Design Project.

I ACLs implemented to **control and restrict network access**, particularly for **management and remote access**, following security best practices.

The focus of this section is to ensure that **only authorized users and devices** can access critical network infrastructure.

## 📂 Contents

| File | Description |
|-----|-------------|
| **[01-Restrict-SSH-Access-With-ACL-For-IT-Department.md](./01-Restrict-SSH-Access-With-ACL-For-IT-Department.md)** | Configures ACLs to restrict SSH access to network devices so only the IT Department is permitted |
| **[Access-Control-List-Reference.md](./Access-Control-List-Reference.md)** | Reference document used to track, document, and manage configured ACLs |

---


## 🛡️ Security Focus

The ACLs in this folder are designed to:
- Limit **remote management access** to authorized IT hosts
- Reduce the attack surface on network devices
- Enforce **least-privilege access** principles
- Support secure device administration in a hospital environment

---

## 📝 Notes

- ACLs are applied consistently across **all managed network devices**
- Loopback interfaces are used for **management access**
- Additional ACLs will be added as the network security design expands
