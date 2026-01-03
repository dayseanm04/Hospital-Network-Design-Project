# 🧠 Enable OSPF for the Subnets on the Access Switches


## ✅ VLANs/Subnets that must be in OSPF (Access Switches)

| Access Switch | VLAN ID | Department / VLAN Name | Subnet (CIDR) | Wildcard Mask | OSPF Area |
|---|---:|---|---|---|---:|
| F1-ASW1 | 101 | Emergency Department | 172.16.1.0/26 | 0.0.0.63 | 1 |
| F1-ASW1 | 110 | X-Ray / Imaging | 172.16.1.64/27 | 0.0.0.31 | 1 |
| F1-ASW2 | 120 | ED Nurse Offices | 172.16.1.96/27 | 0.0.0.31 | 1 |
| F2-ASW1 | 200 | Medical Records / HIM | 172.16.2.0/27 | 0.0.0.31 | 1 |
| F2-ASW2 | 210 | Billing & Finance | 172.16.2.32/27 | 0.0.0.31 | 1 |
| F2-ASW1 | 220 | Human Resources (HR) | 172.16.2.64/27 | 0.0.0.31 | 1 |
| F2-ASW2 | 230 | Insurance | 172.16.2.128/27 | 0.0.0.31 | 1 |
| F3-ASW1 | 300 | Nurse Offices / Nurse Station | 172.16.3.0/26 | 0.0.0.63 | 1 |
| F3-ASW2 | 310 | ICU (Floor 3) | 172.16.3.64/27 | 0.0.0.31 | 1 |
| F3-ASW2 | 330 | Radiology / Imaging (Floor 3) | 172.16.3.128/27 | 0.0.0.31 | 1 |


### ⚙️ Configuration format

#### 🔷 Enter Global Config mode

```bash
enable
configure terminal
```

#### 🔷 Enter OSPF config mode

```bash
router ospf 1
network <network Address> <Wildcard Mask> area 1
```


### 🏥 Example F1-ASW1 (VLAN 101, 110)

```bash
router ospf 1
network 172.16.1.0 0.0.0.63 area 1
```

#### 🔷 Save Config

```bash
end
write memoery
```


