# Configure Layer 3 EtherChannel for DSWs to Service Switch

## Overview

In this task I will configure **Layer 3 LACP EtherChannel** between the **distribution switches (DSW1 and DSW2)** and the **Service Access Switch (Service-ASW)**.

Multiple physical links are bundled together into logical **routed port-channels** using **LACP**.  
This provides **redundancy** and **higher bandwidth** for traffic going to and from network services hosted on the Service-ASW.


## Reference Network Diagram

<img width="895" height="443" alt="net-diagram" src="https://github.com/user-attachments/assets/d68987f7-4d57-4650-8a14-d304f67acaef" />

---

## Devices Involved

| Device | Role |
|------|-----|
| DSW1 | Distribution Switch |
| DSW2 | Distribution Switch |
| Service-ASW | Service Access Switch |

---

## Physical Connectivity

| Service-ASW Interface | Connected Device | Remote Interface |
|---------------------|-----------------|-----------------|
| G1/0/24 | DSW1 | G1/0/13 |
| G1/0/23 | DSW1 | G1/0/14 |
| G1/0/22 | DSW2 | G1/0/13 |
| G1/0/21 | DSW2 | G1/0/14 |

---

## Layer 3 EtherChannel Design

Each DSW–Service-ASW connection uses a **point-to-point /30 network**, with IP addresses assigned to the **Port-Channel interfaces**.

---

## 1️⃣ Configure L3 LACP EtherChannel: DSW1 ↔ Service-ASW

### On DSW1 (Port-Channel 7)

```bash
interface G1/0/13-14
no switchport
channel-group 7 mode active
```

#### Configure Po7

```bash
description To-Service-ASW
ip address 10.255.2.1 255.255.255.252
```

### On **Service-ASW** (Port-Channel 1)

#### Bundle uplinks to DSW1:

```bash
interface range G1/0/23-24
no switchport
channel-group 1 mode active
```

#### Configure Po1

```bashdescription To-DSW1
ip address 10.255.2.2 255.255.255.252
```

---

## 2️⃣ Configure L3 LACP EtherChannel: DSW2 ↔ Service-ASW

### On DSW2 (Port-Channel 7)

```bash
interface G1/0/13-14
no switchport
channel-group 7 mode active
```

#### Configure Po7

```bash
description To-Service-ASW
ip address 10.255.2.5 255.255.255.252
```

### On **Service-ASW** (Port-Channel 2)

#### Bundle uplinks to DSW1:

```bash
interface range G1/0/21-22
no switchport
channel-group 2 mode active
```


#### Configure Po2

```bash
description To-DSW2
ip address 10.255.2.6 255.255.255.252
```

---

## DSW1 ↔ Service-ASW EtherChannel

### Logical Link Details

| Item | Details |
|----|--------|
| Network | 10.255.2.0 /30 |
| DSW1 Port-Channel | Po7 |
| DSW1 Po7 IP | 10.255.2.1 |
| Service-ASW Port-Channel | Po1 |
| Service-ASW Po1 IP | 10.255.2.2 |
| Protocol | LACP (active) |

---

## DSW2 ↔ Service-ASW EtherChannel

### Logical Link Details

| Item | Details |
|----|--------|
| Network | 10.255.2.4 /30 |
| DSW2 Port-Channel | Po7 |
| DSW2 Po7 IP | 10.255.2.5 |
| Service-ASW Port-Channel | Po2 |
| Service-ASW Po2 IP | 10.255.2.6 |
| Protocol | LACP (active) |

---

## Routing Requirement

| Device | Requirement |
|------|------------|
| Service-ASW | IP routing enabled |
| DSW1 / DSW2 | Routed Port-Channels |

This allows Layer 3 forwarding between the service Access Switch and the distribution switches.

---

## Verification 

### show etherchannel summary on DSW1

<img width="837" height="466" alt="DSW1-show-pc" src="https://github.com/user-attachments/assets/edede0a4-e862-4377-9c6e-6d23459daeac" />

### show etherchannel summary on DSW2

<img width="824" height="475" alt="DSW2-show-pc" src="https://github.com/user-attachments/assets/989f923a-52ee-4e17-8a7e-61f3be0cc12e" />

### show etherchannel summary on Service-ASW

<img width="810" height="368" alt="Service-SW-pc" src="https://github.com/user-attachments/assets/2874dd17-78bd-4a68-b8b4-b0afeadf798d" />

### show ip int brief | include Port-channel on Service-ASW

<img width="781" height="99" alt="Service-SW-ip-int" src="https://github.com/user-attachments/assets/737c0688-3cfb-417d-8dce-4f592762c208" />


### show ip int brief | include Port-channel on DSW1
<img width="795" height="202" alt="DSW1-ip-int" src="https://github.com/user-attachments/assets/41786e4a-0cb3-4365-8af8-8ed4b6d3fdd7" />

### show ip int brief | include Port-channel on DSW2

<img width="805" height="207" alt="DSW2-ip-int" src="https://github.com/user-attachments/assets/66233ba5-449f-4ba7-822b-042beb7a80da" />
