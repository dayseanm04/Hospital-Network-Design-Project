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


## 🔌 Physical Connections

| Device | Interface | Connected To |
|--------|-----------|--------------|
| INET-WS1 | NIC | ISP1-R1 G1/0/24 |
| INET-WS2 | NIC | ISP1-R1 G1/0/23 |

---

## 🏷️ VLAN 222 Configuration (On ISP1-R1)

### Create VLAN

```bash
vlan 222
 name INET-Web-SRVs
```

### Assign Interfaces to VLAN 222

```bash
interface range g1/0/23-24
 switchport access vlan 222
```

###  Configure SVI for VLAN 222

```bash
interface vlan 222
 ip address 70.70.70.1 255.255.255.0
```

###  Enable HTTP on Web Servers

On each server:

1. Open the server
2. Navigate to Services then click on HTTP
3. Turn HTTP ON
4. Turn off the other services

### 🛣️ Static Route Configuration

On INET-SW:

```bash
ip route 70.70.70.0 255.255.255.0 10.30.30.1
```




