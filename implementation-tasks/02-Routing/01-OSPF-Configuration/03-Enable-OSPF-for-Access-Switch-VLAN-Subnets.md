# Enable OSPF for the Subnets on the Access Switches


## VLANs/Subnets that must be in OSPF (Access Switches)

| Access Switch | VLAN ID | Department / VLAN Name | Subnet (CIDR) | Wildcard Mask | OSPF Area |
|---|---:|---|---|---|---:|
| F1-ASW1 | 101 | Emergency Department | 172.16.1.0/26 | 0.0.0.63 | 1 |
| F1-ASW1 | 110 | X-Ray / Imaging | 172.16.1.64/27 | 0.0.0.31 | 1 |
| F1-ASW2 | 120 | ED Nurse Offices | 172.16.1.96/27 | 0.0.0.31 | 1 |
| F2-ASW1 | 200 | Medical Records / HIM | 172.16.2.0/27 | 0.0.0.31 | 1 |
| F2-ASW2 | 210 | Billing & Finance | 172.16.2.32/27 | 0.0.0.31 | 1 |
| F2-ASW1 | 220 | Human Resources (HR) | 172.16.2.64/27 | 0.0.0.31 | 1 |
| F3-ASW1 | 300 | Nurse Offices / Nurse Station | 172.16.3.0/26 | 0.0.0.63 | 1 |
| F3-ASW2 | 310 | ICU (Floor 3) | 172.16.3.64/27 | 0.0.0.31 | 1 |
| F3-ASW2 | 330 | Radiology / Imaging (Floor 3) | 172.16.3.128/27 | 0.0.0.31 | 1 |


### ⚙️ Configuration format

#### Enter Global Config mode

```bash
enable
configure terminal
```

#### Enter OSPF config mode

```bash
router ospf 10
network <network Address> <Wildcard Mask> area 1
```


### Example F1-ASW1 (VLAN 101, 110)

```bash
router ospf 10
network 172.16.1.0 0.0.0.63 area 1
```

#### Save Config

```bash
end
write memory
```

## ✅ Verify

#### On DSW1 show ip route | include 172

<img width="758" height="222" alt="DSW1-ip-route" src="https://github.com/user-attachments/assets/afb2e462-486c-4d61-bb22-884cffec915f" />

#### On DSW2 show ip route | include 172

<img width="795" height="225" alt="DSW2-ip-route" src="https://github.com/user-attachments/assets/d56d4cf0-fe57-4269-92eb-ce1b7969b52f" />

DSW1 & DSW2 succesfully learned the route to the subnets VIA OSPF!
