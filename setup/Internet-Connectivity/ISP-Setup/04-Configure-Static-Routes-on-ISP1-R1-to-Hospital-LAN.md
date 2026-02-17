# 🌐 Configure Static Routes on ISP1-R1 to Hospital LAN

## 📌 Overview
This task, I will configure static routes on **ISP1-R1** so it can reach the Hospital LAN. These routes allow ISP1 to properly return traffic to the hospital after NAT translation.


## Reference Topology

<img width="391" height="299" alt="topology" src="https://github.com/user-attachments/assets/62090ef2-aa08-4f17-b0bf-7b54a2e56c3c" />

## 🎯 Objective
- Configure static routes toward hospital NAT pools
- Ensure return traffic from ISP1 reaches the correct edge router

---

## 🔧 Configuration on ISP1-R1

```bash
ip route 100.100.100.0 255.255.255.252 69.45.12.2
ip route 200.200.200.0 255.255.255.252 100.45.12.2
```

#### Route Explanation

| Destination Network | Purpose                     | Next Hop    |
| ------------------- | --------------------------- | ----------- |
| 100.100.100.0/30    | NAT Pool used by HS-EDGE-R1 | 69.45.12.2  |
| 200.200.200.0/30    | NAT Pool used by HS-EDGE-R2 | 100.45.12.2 |

Note: 
- 100.100.100.0/30 and 200.200.200.0/30 are public IP ranges used for NAT translations
- I used static route to demonstrate the Hospital LAN can reach the internet. (CCNA level)
- MPLS or BGP is not implemented in this project


