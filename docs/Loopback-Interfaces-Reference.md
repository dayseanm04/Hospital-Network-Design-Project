# 🔁 Loopback Interfaces Reference

**Purpose:**  
Loopback interfaces provide **stable IP addresses** for routing protocols (OSPF router IDs), management, and troubleshooting.  
All loopbacks use a **/32 mask** (single-host address).

---

## 📋 Loopback IP Address Table

| Device | Loopback Interface | IP Address (/32) | Notes |
|---|---|---|---|
| **F1-ASW1** | Loopback0 | 10.0.0.1/32 | Floor 1 access switch |
| **F1-ASW2** | Loopback0 | 10.0.0.2/32 | Floor 1 access switch |
| **F2-ASW1** | Loopback0 | 10.0.0.3/32 | Floor 2 access switch |
| **F2-ASW2** | Loopback0 | 10.0.0.4/32 | Floor 2 access switch |
| **F3-ASW1** | Loopback0 | 10.0.0.5/32 | Floor 3 access switch |
| **F3-ASW2** | Loopback0 | 10.0.0.6/32 | Floor 3 access switch |
| **Service-ASW** | Loopback0 | 10.0.0.7/32 | Service access switch |
| **DSW1** | Loopback0 | 10.0.0.10/32 | Distribution switch |
| **DSW2** | Loopback0 | 10.0.0.11/32 | Distribution switch |
| **HS-CORE-R1** | Loopback0 | 10.10.0.15/32 | Core router loopback |
| **HS-CORE-FW1** | Router ID | 10.0.0.20/32 | Used as OSPF Router ID |

---

## 📋 Internet side / ISP side Loopback IP Address Table

| Device | Loopback Interface | IP Address (/32) | Notes |
|---|---|---|---|
| **ISP1-R1** | Loopback0 | 10.10.10.10/32 | ISP1-R1 |
| **ISP2-R1** | Loopback0 | 10.10.10.20/32 | ISP2-R1 |


## 🛠️ How Loopbacks Are Configured (Generic)
On each device (in **global config mode**):
- Create the loopback interface: `interface loopback0`
- Assign the IP address shown above
- Loopbacks are **always up**, no `no shutdown` needed
