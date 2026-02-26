# Configure OSPF Passive Interfaces (OSPF Optimization)

## Overview

In this task, I will configure **OSPF passive interfaces for VLANs on the access switches** so that **OSPF routing updates are not sent or received on user VLANs**.

The VLAN networks remain advertised in OSPF, but **end devices do not participate in OSPF neighbor formation**, which improves security and reduces unnecessary routing traffic.

---

## Objective

- Prevent OSPF hello packets on end-user VLANs
- Reduce OSPF overhead on the access layer

---

## VLANs to Make Passive

| Access Switch | VLANs (Passive) |
|-------------|------------------|
| **F1-ASW1 and F1-ASW2** | 101, 110, 120 |
| **F2-ASW1 and F2-ASW2** | 200, 210, 220 |
| **F3-ASW1 and F3-ASW2** | 300, 310, 330 |
| **Service-ASW1** | 240, 700 |

---

## Configuration Steps

### 1️⃣ Enter OSPF configuration mode
```bash
router ospf 10
```

### 2️⃣ Configure passive interfaces for the VLANs on that switch

```bash
passive-interface Vlan <VLAN-ID>
end
```

### Save Configuration

```bash
write memory
```

## Verification (Run on ALL Access Switches)

#### 🔷 show ip protocols on F1-ASW1

<img width="792" height="402" alt="F1-ASW1" src="https://github.com/user-attachments/assets/87ba7951-7a5d-4666-8dcb-679ac205a61f" />


#### 🔷 show ip protocols on F1-ASW2

<img width="811" height="403" alt="F1-ASW2" src="https://github.com/user-attachments/assets/072186ed-4519-4714-86d5-ab8cf50bde9d" />


#### 🔷 show ip protocols on F2-ASW1

<img width="811" height="405" alt="F2-ASW1" src="https://github.com/user-attachments/assets/3c055a92-dd2e-4865-bf8c-ed808dfbf8dd" />


#### 🔷 show ip protocols on F2-ASW2

<img width="800" height="380" alt="F2-ASW2" src="https://github.com/user-attachments/assets/36955ccf-f4f7-4f31-ab68-3a46ce93c0af" />


#### 🔷 show ip protocols on F3-ASW1

<img width="802" height="383" alt="F3-ASW1" src="https://github.com/user-attachments/assets/7a8d1086-ed55-45e7-bda0-15d8df030ea2" />


#### 🔷 show ip protocols on F3-ASW2

<img width="805" height="431" alt="F3-ASW2" src="https://github.com/user-attachments/assets/6d735c4b-89b7-4ffd-b269-b2774a9075bd" />


#### 🔷 show ip protocols on Service-ASW

<img width="727" height="315" alt="Service-ASW" src="https://github.com/user-attachments/assets/cf965b2d-fb49-4093-9ade-66c2f4f70e99" />

Note: I changed the process ID  to 10
