# 🔗 Configure Layer 3 EtherChannel for DSWs to ASWs

## 📌 Overview
In this task I will configure **Layer 3 EtherChannels** between the **Distribution Switches (DSW1 and DSW2)** and the **Access Switches (ASWs)**.

I removed the **Layer 2 port-channels** and replaced with **routed EtherChannels** using **LACP**.  
Each DSW–ASW connection uses a dedicated **point-to-point /30 network**, allowing the access layer.

This approach provides:
- Better scalability
- Faster convergence
- Simplified troubleshooting
- Reduced Layer 2 dependency

## Reference Diagram

<img width="539" height="341" alt="topology" src="https://github.com/user-attachments/assets/ec132bce-d3eb-40b6-b22b-b0d694a93232" />


---

## 🧹 Part A - Remove OLD L2 EtherChannels (Trunks)

### 1️⃣ Remove L2 Port-Channels on **DSW1 and DSW2 (Po1–Po6)**

#### 🔷In global config moderemove Po1 through Po6 (repeat for each Po#):  

```bash
no interface po1
```

**repeat for po2–po6**

### 🔷 Then revert the member interfaces (**G1/0/1–12**):  

Remove trunk/L2 configurations and re-enable interfaces:  

```bash
no switchport
no switchport mode trunk
no switchport trunk allowed vlan #,#
no shutdown
```

**Note📌" The # is the vlan number**

### 2️⃣ Remove L2 Port-Channels on **Access Switches (Po1–Po2)**

#### 🔷 On **each ASW**, remove the existing L2 port-channels:  

```bash
no interface po1
no interface po2
```

#### 🔷 Then remove the trunk allowed VLANs and bring links up:  

```bash
no switchport trunk allowed vlan #,#
no shutdown
```

## 🔁 Part B - Configure L3 LACP EtherChannels (Routed Port-Channels)

### 3️⃣ L3 EtherChannel Command Template (Use This Everywhere)
On **both sides** of the EtherChannel:

**Member interfaces**
- `interface range g1/0/x-y`
- `no switchport`
- `channel-group <#> mode active`

**Port-channel interface**
- `interface po<#>`
- `description <to-where>`
- `ip address <IP> 255.255.255.252`

---



## 🔄 Design Change Summary

| Before | After |
|------|------|
| Layer 2 Port-Channels | Layer 3 Routed EtherChannels |
| Trunk links | Point-to-point routed links |


## 🌐 Layer 3 Point-to-Point Networks

Each DSW–ASW connection uses a dedicated **/30 subnet**.

---

## 🏢 Floor 1 – Access Switches

### 🔹 DSW1 ↔ F1-ASW1

| Item | Details |
|----|--------|
| Network | 10.10.0.0 /30 |
| DSW1 Po1 IP | 10.10.0.1 |
| F1-ASW1 Po1 IP | 10.10.0.2 |
| EtherChannel | Po1 |

---

### 🔹 DSW2 ↔ F1-ASW1

| Item | Details |
|----|--------|
| Network | 10.20.0.0 /30 |
| DSW2 Po1 IP | 10.20.0.1 |
| F1-ASW1 Po2 IP | 10.20.0.2 |
| EtherChannel | Po2 |

---

### 🔹 DSW1 ↔ F1-ASW2

| Item | Details |
|----|--------|
| Network | 10.10.0.4 /30 |
| DSW1 Po2 IP | 10.10.0.5 |
| F1-ASW2 Po1 IP | 10.10.0.6 |
| EtherChannel | Po2 |

---

### 🔹 DSW2 ↔ F1-ASW2

| Item | Details |
|----|--------|
| Network | 10.20.0.4 /30 |
| DSW2 Po2 IP | 10.20.0.5 |
| F1-ASW2 Po2 IP | 10.20.0.6 |
| EtherChannel | Po2 |

---

## 🏥 Floor 2 – Access Switches

### 🔹 DSW1 ↔ F2-ASW1

| Item | Details |
|----|--------|
| Network | 10.10.0.8 /30 |
| DSW1 Po3 IP | 10.10.0.9 |
| F2-ASW1 Po1 IP | 10.10.0.10 |
| EtherChannel | Po3 |

---

### 🔹 DSW1 ↔ F2-ASW2

| Item | Details |
|----|--------|
| Network | 10.20.0.12 /30 |
| DSW1 Po3 IP | 10.20.0.9 |
| F2-ASW2 Po1 IP | 10.20.0.10 |
| EtherChannel | Po3 |

---

### 🔹 DSW1 ↔ F2-ASW1

| Item | Details |
|----|--------|
| Network | 10.10.0.12 /30 |
| DSW1 Po4 IP | 10.10.0.13 |
| F2-ASW1 Po2 IP | 10.10.0.14 |
| EtherChannel | Po4 |

---


### 🔹 DSW2 ↔ F2-ASW2

| Item | Details |
|----|--------|
| Network | 10.20.0.12 /30 |
| DSW2 Po4 IP | 10.20.0.13 |
| F2-ASW2 Po1 IP | 10.20.0.14 |
| EtherChannel | Po4 |

---

## 🏬 Floor 3 – Access Switches

### 🔹 DSW1 ↔ F3-ASW1

| Item | Details |
|----|--------|
| Network | 10.10.0.16 /30 |
| DSW1 Po5 IP | 10.10.0.17 |
| F3-ASW1 Po1 IP | 10.10.0.18 |
| EtherChannel | Po5 |

---

### 🔹 DSW2 ↔ F3-ASW1

| Item | Details |
|----|--------|
| Network | 10.20.0.16 /30 |
| DSW2 Po5 IP | 10.20.0.17 |
| F3-ASW1 Po2 IP | 10.20.0.18 |
| EtherChannel | Po5 |

---

### 🔹 DSW1 ↔ F3-ASW2

| Item | Details |
|----|--------|
| Network | 10.10.0.20 /30 |
| DSW1 Po6 IP | 10.10.0.21 |
| F3-ASW2 Po1 IP | 10.10.0.22 |
| EtherChannel | Po6 |

---

### 🔹 DSW2 ↔ F3-ASW2

| Item | Details |
|----|--------|
| Network | 10.20.0.20 /30 |
| DSW2 Po6 IP | 10.20.0.21 |
| F3-ASW2 Po2 IP | 10.20.0.22 |
| EtherChannel | Po6 |

---

## ✅ Verification

### show etherchannel summary on DSW1

<img width="837" height="466" alt="DSW1-show-pc" src="https://github.com/user-attachments/assets/edede0a4-e862-4377-9c6e-6d23459daeac" />

### show etherchannel summary on DSW2

<img width="824" height="475" alt="DSW2-show-pc" src="https://github.com/user-attachments/assets/989f923a-52ee-4e17-8a7e-61f3be0cc12e" />

### show etherchannel summary on F1-ASW1

<img width="820" height="387" alt="F1-ASW1-sh-et-su" src="https://github.com/user-attachments/assets/c13a72bf-171f-4df1-a207-4278c77b2989" />

### show etherchannel summary on F1-ASW2

<img width="840" height="370" alt="F1-ASW2-sh-et-su" src="https://github.com/user-attachments/assets/278f21a5-f5b9-4050-bf53-2b9084604647" />


### show etherchannel summary on F2-ASW1

<img width="815" height="383" alt="F2-ASW1-sh-et-su" src="https://github.com/user-attachments/assets/7d916051-03f9-4fe3-8c27-cc1c59217922" />


### show etherchannel summary on F2-ASW2

<img width="779" height="388" alt="F2-ASW2-sh-et-su" src="https://github.com/user-attachments/assets/35d8d602-5f39-4607-aca2-be322d01aa4a" />


### show etherchannel summary on F3-ASW1

<img width="829" height="371" alt="F3-ASW1-sh-et-su" src="https://github.com/user-attachments/assets/55591399-1b2e-4689-becf-33841a347f67" />


### show etherchannel summary on F3-ASW2

<img width="737" height="387" alt="F3-ASW2-sh-et-su" src="https://github.com/user-attachments/assets/af9ba88d-4c55-4226-8d64-bb5700826a44" />


### show ip int brief | include Port-channel on F1-ASW1

<img width="766" height="101" alt="F1-ASW1-show-ip-int-brief" src="https://github.com/user-attachments/assets/01b83a18-b4f5-4548-bab2-bb0f6060b8d4" />


### show ip int brief | include Port-channel on F1-ASW2

<img width="790" height="99" alt="F1-ASW2-show-ip-int-brief" src="https://github.com/user-attachments/assets/024e997f-9b87-4be3-ae40-4f2654ed9965" />


### show ip int brief | include Port-channel on F2-ASW1

<img width="779" height="96" alt="F2-ASW1-show-ip-int-brief" src="https://github.com/user-attachments/assets/35ff864d-83ef-409c-8a86-73e20d8b628d" />


### show ip int brief | include Port-channel on F2-ASW2

<img width="786" height="101" alt="F2-ASW2-show-ip-int-brief" src="https://github.com/user-attachments/assets/7cb723b7-3c08-4548-b0ad-16b40b73d801" />


### show ip int brief | include Port-channel on F3-ASW1

<img width="766" height="103" alt="F3-ASW1-show-ip-int-brief" src="https://github.com/user-attachments/assets/0a83d736-3431-4294-98d0-595b6474201a" />


### show ip int brief | include Port-channel on F3-ASW2

<img width="768" height="101" alt="F3-ASW2-show-ip-int-brief" src="https://github.com/user-attachments/assets/ed3d3b61-5d3c-40ce-a9e8-1f2008ee2774" />













