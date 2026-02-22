# Configure SVIs on the Access Switches (Default Gateways)

**Goal:** Configure **SVIs** on each Access Switch so VLANs have a **default gateway** for routing.

## Refernce Netork Diagram

<img width="551" height="147" alt="reference-network-diagram" src="https://github.com/user-attachments/assets/530bc025-1921-4b91-89a4-ce4868f8dffb" />

---

## SVI IP Plan

### F1-ASW1 SVIs

| VLAN | Department| SVI IP (Gateway) | Subnet Mask |
|---:|---|---|---|
| 101 | Emergency Department (ED) | 172.16.1.1 | 255.255.255.192 |
| 110 | X-Ray / Imaging | 172.16.1.65 | 255.255.225.224 |

---

### F1-ASW2 SVIs

| VLAN | Department| SVI IP (Gateway) | Subnet Mask |
|---:|---|---|---|
| 120 | ED Nurse Offices| 172.16.1.97 | 255.255.225.224 |

---

### F2-ASW1 SVIs

| VLAN | Department| SVI IP (Gateway) | Subnet Mask |
|---:|---|---|---|
| 200 | Medical Records / HIM | 172.16.2.1 | 255.255.225.224 |
| 220 | Human Resources (HR) |172.16.1.65 | 255.255.255.224 |

---

### F2-ASW2 SVIs

| VLAN | Department| SVI IP (Gateway) | Subnet Mask |
|---:|---|---|---|
| 210 | Billing & Finance | 172.16.2.33 | 255.255.255.224 |

---

### F3-ASW1 SVIs

| VLAN | Department| SVI IP (Gateway) | Subnet Mask |
|---:|---|---|---|
| 300 | Nurse Offices | 172.16.3.1 | 255.255.225.192 |

---

### F3-ASW2 SVIs

| VLAN | Department| SVI IP (Gateway) | Subnet Mask |
|---:|---|---|---|
| 310 | ICU (Floor 3) |172.16.3.65 | 255.255.255.224 |
| 330 | Radiology / Imaging |172.16.3.129 | 255.255.255.224 |

---

## Step-by-Step Configuration

### Enter global configuration mode

```bash
enable
conf t
```

### Create the SVIs listed for that switch

#### Use this pattern for each VLAN:

```bash
interface vlan <VLAN>
ip address <IP> <MASK>
no shutdown
exit
```

**Note: sicne you will be typing many IP addresses pay close attention**

### Save

```bash
end
write memory
```

#### Note: I did not configure an SVI for every single VLAN because it would be unnecessary and repetitive for the scope of this project, as the core concepts and functionality are already clearly shown. I configured SVIs for most VLANs.

## Verification

### Confirm SVIs are up

#### show ip int brief | include Vlan on F1-ASW1

<img width="787" height="101" alt="F1-ASW1" src="https://github.com/user-attachments/assets/3f57317a-b53b-4ae2-beb4-bac14dce698d" />

#### show ip int brief | include Vlan on F1-ASW2

<img width="852" height="83" alt="F1-ASW2" src="https://github.com/user-attachments/assets/62c54601-379d-44a0-8932-2e0b2f83605c" />

#### show ip int brief | include Vlan on F2-ASW1

<img width="828" height="119" alt="F2-ASW1" src="https://github.com/user-attachments/assets/2bf3f6d9-02f4-4dc6-a157-b4566f9b4bc0" />

#### show ip int brief | include Vlan on F2-ASW2

<img width="816" height="81" alt="F2-ASW2" src="https://github.com/user-attachments/assets/6b990b14-1f43-48f4-914b-0c66080410c8" />

#### show ip int brief | include Vlan on F3-ASW1

<img width="817" height="101" alt="F3-ASW1" src="https://github.com/user-attachments/assets/52dcd7d5-f801-459b-b9c7-9c8687cf4f4a" />

#### show ip int brief | include Vlan on F3-ASW2

<img width="803" height="119" alt="F3-ASW2" src="https://github.com/user-attachments/assets/4cdfd61f-328a-48b5-be34-4690ffaab4e9" />
