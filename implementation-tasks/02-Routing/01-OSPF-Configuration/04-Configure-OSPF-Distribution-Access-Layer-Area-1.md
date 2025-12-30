# 🛰️ Configure OSPF Between DSWs and ASWs (Area 1)

**Goal:** Enable **OSPF process 1 (Area 1)** on:
- **DSW1 + DSW2** (all /30 port-channel links to access switches)
- **All ASWs** (their loopbacks + their /30 uplinks to DSW1 + DSW2)
- **Service-ASW** (loopback + uplinks to DSWs + server subnet)

## Rerence Network Diagram

<img width="879" height="397" alt="reference-area" src="https://github.com/user-attachments/assets/6ac5a6f6-dc7b-4142-8983-e5f2868a504b" />

---


# 🟦 Part A - Configure OSPF on DSW1

## 1️⃣ Enable OSPF on DSW1 (Area 1)

### ♦️ On DSW1 in global config mode:

```bash
router ospf 1
network 10.10.0.0 0.0.0.255 area 1
```

✅ **This enables OSPF on all DSW1 port-channels** going to the ASWs because they all fall inside **10.10.0.0/24** (each link is /30).

## 2️⃣ Also enable OSPF on DSW1 → Service-ASW P2P link

### ♦️ Still under router ospf 1:

```bash
network 10.255.2.0 0.0.0.3 area 1
```

---

# 🟧 Part B - Configure OSPF on DSW2

## 3️⃣ Enable OSPF on DSW2 (Area 1)

#### ♦️ DSW2 in global config mode:

```bash
router ospf 1
network 10.20.0.0 0.0.0.255 area 1
```

✅ **This enables OSPF on all DSW2 port-channels** going to the ASWs because they all fall inside **10.10.0.0/24** (each link is /30).

## 4️⃣ Also enable OSPF on DSW2 → Service-ASW P2P link

#### ♦️ Still under `router ospf 1`:

```bash
network 10.255.2.4 0.0.0.3 area 1
```

---

# 🟩 Part C - Configure OSPF on Access Switches (ASWs)

## 5️⃣ F1-ASW1

#### ♦️ On F1-ASW1:

- `router ospf 1`
- `network 10.0.0.1 0.0.0.0 area 1`  *(loopback)* 
- `network 10.10.0.0 0.0.0.3 area 1` *(to DSW1)* 
- `network 10.20.0.0 0.0.0.3 area 1` *(to DSW2)*

---

## 6️⃣ F1-ASW2

#### ♦️ On F1-ASW2:

- `router ospf 1`
- `network 10.0.0.2 0.0.0.0 area 1` *(loopback)*
- `network 10.10.0.4 0.0.0.3 area 1` *(to DSW1)*
- `network 10.20.0.4 0.0.0.3 area 1` *(to DSW2)* 

---

## 7️⃣ F2-ASW1
#### ♦️ On F2-ASW1:

- `router ospf 1`
- `network 10.0.0.3 0.0.0.0 area 1` *(loopback)* 
- `network 10.10.0.8 0.0.0.3 area 1` *(to DSW1)*
- `network 10.20.0.8 0.0.0.3 area 1` *(to DSW2)* 

---

## 8️⃣ F2-ASW2

#### ♦️ On F2-ASW2:

- `router ospf 1`
- `network 10.0.0.4 0.0.0.0 area 1` *(loopback)* 
- `network 10.10.0.12 0.0.0.3 area 1` *(to DSW1)* 
- `network 10.20.0.12 0.0.0.3 area 1` *(to DSW2)*

---

## 9️⃣ F3-ASW1

#### ♦️ On F3-ASW1:

- `router ospf 1`
- `network 10.0.0.5 0.0.0.0 area 1` *(loopback)*
- `network 10.10.0.16 0.0.0.3 area 1` *(to DSW1)* 
- `network 10.20.0.16 0.0.0.3 area 1` *(to DSW2)* 

---

## 🔟 F3-ASW2

#### ♦️ On F3-ASW2:

- `router ospf 1`
- `network 10.0.0.6 0.0.0.0 area 1` *(loopback)*
- `network 10.10.0.20 0.0.0.3 area 1` *(to DSW1)*
- `network 10.20.0.20 0.0.0.3 area 1` *(to DSW2)*

---


# 🟪 Part D - Configure OSPF on Service-ASW

## 1️⃣1️⃣ Enable OSPF for Service-ASW loopback + uplinks

#### ♦️ On Service-ASW:

- `router ospf 1`
- `network 10.0.0.7 0.0.0.0 area 1` *(loopback)* 
- `network 10.255.2.0 0.0.0.3 area 1` *(to DSW1)*
- `network 10.255.2.4 0.0.0.3 area 1` *(to DSW2)*

## 1️⃣2️⃣ Enable OSPF on the Server VLAN subnet

#### ♦️ Still under `router ospf 1`:

- `network 10.10.10.0 0.0.0.31 area 1` 

> ✅ Note: /27 mask (255.255.255.224) has the wildcard mask of: **0.0.0.31**. 


# ✅ Verification (Run on a few devices)

## 1️⃣3️⃣ Check neighbors

#### ♦️ show ip ospf neighbor on DSW1

<img width="878" height="263" alt="DSW1-OSPF-Neighbors" src="https://github.com/user-attachments/assets/a8a40b86-04c4-4d9c-9cd8-71eb5cb16483" />

#### ♦️ show ip ospf neighbor on DSW2

<img width="889" height="259" alt="DSW2-OSPF-Neighbors" src="https://github.com/user-attachments/assets/3f97e16e-cf4b-4506-95db-3e88c2165ab2" />

#### ♦️ show ip ospf neighbor on F1-ASW1

<img width="887" height="134" alt="F1-ASW1-ospf-neighbors" src="https://github.com/user-attachments/assets/08ce89aa-7034-4210-8b76-c8db82843ff3" />

#### ♦️ show ip ospf neighbor on F1-ASW2

<img width="825" height="138" alt="F1-ASW2-ospf-neighbors" src="https://github.com/user-attachments/assets/2e4df59c-30f2-4751-9cdd-0bc1dc72c80f" />

#### ♦️ show ip ospf neighbor on F2-ASW1

<img width="840" height="136" alt="F2-ASW1-ospf-neighbors" src="https://github.com/user-attachments/assets/649e3b4e-dccf-43f7-abc9-363ee4092362" />

#### ♦️ show ip ospf neighbor on F2-ASW2

















