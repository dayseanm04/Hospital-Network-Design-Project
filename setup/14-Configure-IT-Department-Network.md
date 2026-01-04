# Setup IT Department Network 

## 🎯 Goal

Set up the **IT Department** on the **Service-ASW** by creating **VLAN 240**, assigning ports for IT PCs, configuring the 
**SVI (default gateway)**, and configuring **static IPs** on the IT PCs.

## Refernce Network Diagram

<img width="446" height="178" alt="reference-network-diagram" src="https://github.com/user-attachments/assets/12fda8fc-4dde-4434-848d-2d194839adfe" />

---

## 🌐 IT Department Network Info
| Item | Value |
|---|---|
| VLAN | **240**  |
| VLAN Name | **IT-DPT** |
| Subnet | **10.50.50.0/26** |
| SVI / Default Gateway | **10.50.50.1/26**  |
| Subnet Mask | **255.255.255.192** |

---

## 🔌 PC Connections
| Device | Switch | Port |
|---|---|---|
| IT-PC1 | Service-ASW | **G1/0/9** |
| IT-PC2 | Service-ASW | **G1/0/10** |

---

# 🛠️ Step-by-Step Configuration (Service-ASW)

## 1️⃣ Enter global configuration mode

```bashenable
configure terminal
```

---

## 2️⃣ Create the IT Department VLAN

```bash
vlan 240
name IT-DPT
exit
```

---

## 3️⃣ Assign access ports to VLAN 240

```bash
interface range g1/0/9 - 16
switchport access vlan 240
```

---

## 4️⃣ Configure the SVI (Default Gateway) for VLAN 240

```bash
interface vlan 240
ip address 10.50.50.1 255.255.255.192
```

---

## 5️⃣ Save the configuration

```bash
end
write memory
```

---

# 🖥️ Configure Static IPs on IT PCs

## 6️⃣ IT-PC1 IP settings

| Field | Value |
|---|---|
| IP Address | **10.50.50.2**  |
| Subnet Mask | **255.255.255.192** (/26) |
| Default Gateway | **10.50.50.1**  |

## 7️⃣ IT-PC2 IP settings

| Field | Value |
|---|---|
| IP Address | **10.50.50.3** |
| Subnet Mask | **255.255.255.192** (/26)  |
| Default Gateway | **10.50.50.1** |

---

###  [Click here for the connectivity tests](/testing/04-Connectivity-Tests/06-Test-IT-DPT-Connectivity.md)




