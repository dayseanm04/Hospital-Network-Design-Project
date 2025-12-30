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

### ♦️ DSW2 in global config mode:

```bash
router ospf 1
network 10.20.0.0 0.0.0.255 area 1
```

✅ **This enables OSPF on all DSW2 port-channels** going to the ASWs because they all fall inside **10.10.0.0/24** (each link is /30).

## 4️⃣ Also enable OSPF on DSW2 → Service-ASW P2P link

### ♦️ Still under `router ospf 1`:

```bash
network 10.255.2.4 0.0.0.3 area 1
```

---


