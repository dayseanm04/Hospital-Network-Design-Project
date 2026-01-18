# 📡 Advertise Default Route into OSPF

## 📌 Overview
In this task, I will advertise the **default route (0.0.0.0/0)** into the hospital’s **internal OSPF routing domain** so internal router and switches know how to reach the internet.

The core firewall acts as the **OSPF Autonomous System Boundary Router (ASBR)** for the hospital network, and injects the default route into the hospital network/OSPF domain.

### ✅ Click ➡️ [here for the configure Default route on the HS-CORE-FW1 Task.](/implementation-tasks/02-Routing/Configure-Default-Routes-for-Internet-Access.md) 


## Reference Topology

<img width="968" height="310" alt="reference-topology" src="https://github.com/user-attachments/assets/87fc634c-6ce6-49ac-b1c1-fa64cdf7a90a" />

---

## 🎯 Objectives
- Advertise the internet default route into **OSPF**
- Allow internal devices to learn the route to foward internet traffic to

## 🖥 Device Involved
- **HS-CORE-FW1**

## 🧭 Note
- **HS-CORE-FW1** functions as the **OSPF ASBR**
- The default route is injected into **Area 0**
- No OSPF adjacency is formed with ISP devices

## ⚙️ OSPF Default Route Advertisement (HS-CORE-FW1)

Enter global configuration mode on **HS-CORE-FW1**, then advertise the default route:

```bash
router ospf 1
default-information originate
```

**Note:** This command injects 0.0.0.0/0 into OSPF, allowing internal routers and switches to forward internet-bound traffic toward the firewall.

## 🧪 Verification

#### 🟢 On Service-ASW show ip route | include 0.0.0.0

<img width="884" height="99" alt="verify-default-route" src="https://github.com/user-attachments/assets/4a5f2c27-bae4-495d-8485-8eb2fb2da4a8" />

The default route was successfully advertised into the hospitals domain. Note that all of the access switches also learned the path to the internet!
