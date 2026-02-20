# 🌐 06 – Deploy INET Web Servers and Configure VLAN 222

In this task, I deploy two new **INET web servers (INET-WS1 and INET-WS2)** and configure a dedicated **VLAN 222** to support a separate web services segment.  

## Reference Toplogy

<img width="869" height="454" alt="1" src="https://github.com/user-attachments/assets/28cb9363-c91f-4f47-948d-9160d27bbabe" />


## 🎯 Objectives

- Add two new INET web servers
- Create VLAN 222 for web services
- Configure SVI for inter-VLAN routing
- Assign static IP addresses to web servers
- Enable HTTP service
- Configure static routes for reachability

---

## 🖥️ New Web Servers

| Server | IP Address | Subnet | Default Gateway | DNS |
|--------|------------|--------|----------------|-----|
| INET-WS1 | 70.70.70.10 | 255.255.255.0 | 70.70.70.1 | 200.10.0.2 |
| INET-WS2 | 70.70.70.20 | 255.255.255.0 | 70.70.70.1 | 200.10.0.2 |

---

