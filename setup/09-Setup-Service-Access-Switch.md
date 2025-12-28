# 🖧 Setup a Service Switch (Service-ASW)

## 📌 Overview
The **Service Access Switch (Service-ASW)** is used to connect and support internal network services such as **DHCP**.  
It acts as a dedicated switch for servers that provide essential services to the hospital network.

This setup step focuses on preparing the Service-ASW by:
- Assigning the hostname  
- Documenting physical connections to the distribution switches  
- Adding clear interface descriptions for easier management and troubleshooting  

I will configure **EtherChannel**, and **Routing**, and in the implementation tasks to keep the setup process organized and easy to follow.

---

## 🧱 Device Information

| Attribute | Value |
|---------|------|
| Device Role | Service Access Switch |
| Model | Cisco 3650-24PS |
| Hostname | Service-ASW |
| Layer | Access / Services Layer |
| Purpose | Host service (DHCP, DNS, NTP) |

---

## 🔌 Physical Connectivity

### 🔗 Uplink Connections

| Service-ASW Interface | Connected Device | Remote Interface |
|---------------------|-----------------|-----------------|
| G1/0/24 | DSW1 | G1/0/13 |
| G1/0/23 | DSW1 | G1/0/14 |
| G1/0/22 | DSW2 | G1/0/13 |
| G1/0/21 | DSW2 | G1/0/14 |

I configured Interface descriptions on **Service-ASW**, **DSW1**, and **DSW2** to identify these links 

---


