# 🖥️ 01 – Setup DHCP Server (IP Addressing + Connection to Service-ASW)

## 📌 Overview
In this task I will connect the **DHCP server (DHCP-SRV)** to the **Service Access Switch (Service-ASW)** and assigns IP addresses on both ends of the link.


---

## 🔌 Physical Connection

| Device | Interface | Connects To | Interface |
|--------|-----------|------------|-----------|
| DHCP-SRV | G0 | Service-ASW | G1/0/1 |

The DHCP server is connected directly to the Service-ASW.

---

## 🌐 Network Used (DHCP Server ↔ Service Switch)

| Item | Details |
|------|--------|
| Network | 10.10.10.0 /30 |
| Subnet Mask | 255.255.255.252 |
| Purpose | Point-to-point link between DHCP-SRV and Service-ASW |

---

## 🏷️ IP Addressing Plan

| Item | Details |
|------|--------|
| Service-ASW G1/0/1 IP | 10.10.10.1 /30 |
| DHCP-SRV G0 IP | 10.10.10.2 /30 |
| DHCP-SRV Default Gateway | 10.10.10.1 |

The switch interface connected to the DHCP server is configured as a **routed port** with the IP address above}

---

## 🧪 Verification

### show ip interface brief | include GigabitEthernet1/0/1

<img width="811" height="261" alt="service-sw-show-ip-int-brief" src="https://github.com/user-attachments/assets/0ff107d1-a551-4114-92fd-b265a5268ac2" />

### ipconfig on DHCP-SRV

<img width="770" height="397" alt="DHCP-SRV-ipconfig" src="https://github.com/user-attachments/assets/a001ba12-bb2a-469d-b9de-7e3253ac5908" />

