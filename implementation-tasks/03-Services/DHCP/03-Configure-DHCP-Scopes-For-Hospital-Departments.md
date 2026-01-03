# 📦 Configure DHCP Pools (Scopes) – DHCP Server

**Goal:** Configure DHCP pools on the **DHCP-SRV** so client devices on each floor and department automatically receive IP addresses.  

Each pool uses the **SVI (default gateway)** that was already configured on the access switches. 

### ♦️ Find it here: [Configure SVIs on ASWs)](/setup/13-Configure-SVIs-On-Access-Switches.md)

---

## 🏥 DHCP Pool Overview

### 🟦 1st Floor DHCP Pools
| Pool Name | Default Gateway (SVI) | Subnet Mask | Start IP | Max Users |
|---|---|---|---|---|
| Emergency-DPT | 172.16.1.1 | 255.255.255.192 | 172.16.1.2 | 62 |
| X-Ray-DPT | 172.16.1.65 | 255.255.255.224 | 172.16.1.66 | 30 |
| F1-Nurse-Station | 172.16.1.97 | 255.255.255.224 | 172.16.1.98 | 30 |

---
