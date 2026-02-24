# Configure Backbone L3 Port-Channels for Redundancy

## Overview
This task, I will implements**Layer 3 static Port-Channels** across the hospital backbone to provide:

- High availability
- Increased bandwidth
- Redundant routing paths

The backbone includes:
- Edge Routers
- Core Firewalls
- Distribution Switches

---

## Backbone Interconnections

The following Layer 3 Port-Channels form the redundant backbone:

| Connection | Port-Channel | Subnet |
|------------|-------------|--------|
| HS-EDGE-R1 ↔ HS-CORE-FW1 | Po1 | 10.200.0.0/30 |
| HS-EDGE-R2 ↔ HS-CORE-FW2 | Po1 | 10.200.0.4/30 |
| HS-CORE-FW1 ↔ DSW1 | Po20 | 10.255.0.0/30 |
| HS-CORE-FW2 ↔ DSW2 | Po20 | 10.255.0.4/30 |
| HS-EDGE-R1 ↔ HS-EDGE-R2 | Po10 | 10.150.0.0/30 |

---


# 1️⃣ Edge ↔ Core Redundant Links

## HS-EDGE-R1 ↔ HS-CORE-FW1

#### On HS-EDGE-R1 in global config mode:

```bash
interface range g1/1/3-4
 no switchport
 channel-group 1 mode on
```

#### On HS-CORE-FW1 in global config mode:

```bash
interface g1/1
 channel-group 1 mode on
interface g1/2
 channel-group 1 mode on
```

## HS-EDGE-R2 ↔ HS-CORE-FW2

#### On HS-EDGE-R2 in global config mode:

```bash
interface range g1/1/3-4
 no switchport
 channel-group 1 mode on
```

#### On HS-CORE-FW2 in global config mode:

```bash
interface g1/1
 channel-group 1 mode on
interface g1/2
 channel-group 1 mode on
```

## Verification

### show etherchannel summary on HS-EDGE-R1 ✅

<img width="814" height="387" alt="E1" src="https://github.com/user-attachments/assets/7b081811-52e6-417c-8bf7-892caa042591" />

### show etherchannel summary on HS-EDGE-R2 ✅

<img width="827" height="390" alt="E2" src="https://github.com/user-attachments/assets/361841e4-8ffb-4c89-9808-1deb1cbcc0af" />

---

# 2️⃣ Core ↔ Distribution Redundant Links

## HS-CORE-FW1 ↔ DSW1

#### On HS-CORE-FW1 in global config mode:

```bash
interface g1/3
 channel-group 20 mode on
interface g1/4
 channel-group 20 mode on
```

#### On DSW1 in global config mode:

```bash
interface range g1/1/1, g1/1/4
 channel-group 20 mode on
```

## HS-CORE-FW2 ↔ DSW2

#### On HS-CORE-FW2 in global config mode:

```bash
interface g1/3
 channel-group 20 mode on
interface g1/4
 channel-group 20 mode on
```

#### On DSW2 in global config mode:

```bash
interface range g1/1/1, g1/1/4
 channel-group 20 mode on
```

## Verification

### show etherchannel summary on DSW1 ✅

<img width="1005" height="491" alt="DSW1" src="https://github.com/user-attachments/assets/41e7ec85-3f0b-4e3d-9952-fb207c29dc0d" />

### show etherchannel summary on DSW2 ✅

<img width="915" height="479" alt="DSW2" src="https://github.com/user-attachments/assets/1aa16c03-37e6-46f8-80b8-9021c2fea4be" />

---

## 3️⃣ Edge ↔ Edge Redundant Interconnection

## HS-EDGE-R1 to HS-EDGE-R2

#### On HS-EDGE-R1 in global config mode:

```bash
interface range g1/0/23-24
 no switchport
 channel-group 10 mode on
```

#### On HS-EDGE-R2 in global config mode:

```bash
interface range g1/0/23-24
 no switchport
 channel-group 10 mode on
```

## 🔍 Verification

### show etherchannel summary on HS-EDGE-R1 ✅

<img width="814" height="387" alt="E1" src="https://github.com/user-attachments/assets/7b081811-52e6-417c-8bf7-892caa042591" />

### show etherchannel summary on HS-EDGE-R2 ✅

<img width="827" height="390" alt="E2" src="https://github.com/user-attachments/assets/361841e4-8ffb-4c89-9808-1deb1cbcc0af" />
