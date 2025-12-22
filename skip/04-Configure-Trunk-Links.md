# 04 Configure Trunk Links.md

## Skip this step 

➡️ **Skip this step** and complete the following instead:  
[Configure LACP EtherChannel (ASW ↔ DSW Links)](/implementation-tasks/01-Redundancy/01-Configure-LACP-EtherChannel-ASW-DSW-Links.md)


## 🎯 Goal
Configure all **uplink interfaces** as **802.1Q trunk links** between:
- Access Switches (F1/F2/F3) ↔ Distribution Switches (DSW1/DSW2)
- DSW1 ↔ DSW2

## ✅ Standard Trunk Configuration Pattern (don’t repeat full commands)
Use this pattern for **each interface range** in the tables below:

1️⃣ Enter interface range config mode  
- `interface range [INTERFACE_RANGE]`

2️⃣ Configure as trunk  
- `switchport mode trunk`

 ## 💾 Save Configuration
- `write memory`  

---

## 🧱 Part A — Access Switch Uplinks (ASW → DSW)

### 🔌 Trunk Interfaces to Configure (on EVERY Access Switch)
All Access Switches use the same trunk uplink range: **G1/0/21 – G1/0/24**

| Device | Interface Range to Trunk |
|---|---|
| F1-ASW1 | `G1/0/21 - G1/0/24` |
| F1-ASW2 | `G1/0/21 - G1/0/24` |
| F2-ASW1 | `G1/0/21 - G1/0/24` |
| F2-ASW2 | `G1/0/21 - G1/0/24` |
| F3-ASW1 | `G1/0/21 - G1/0/24` |
| F3-ASW2 | `G1/0/21 - G1/0/24` |

### 📝 Uplink Mapping Notes (important)
| Access Switch Uplink Interfaces | Connected To |
|---|---|
| `G1/0/23 - G1/0/24` | DSW1 |
| `G1/0/21 - G1/0/22` | DSW2 |

---

## 🧱 Part B — Distribution Switch Trunks (DSW ←→ Access)

### 🔌 Trunk Interfaces to Configure on DSWs
| Device | Interface Range to Trunk | Purpose |
|---|---|---|
| DSW1 | `G1/0/1 - G1/0/12` | Trunks to Access Switches |
| DSW2 | `G1/0/1 - G1/0/12` | Trunks to Access Switches |

---

## 🔗 Part C — DSW1 ↔ DSW2 Trunk Link

### 🔌 Trunk Interfaces Between DSW1 and DSW2

| Link | Device | Correct Interface Range to Trunk |
|---|---|---|
| DSW1 ↔ DSW2 | DSW1 | `G1/1/2 - G1/1/3` |
| DSW1 ↔ DSW2 | DSW2 | `G1/1/2 - G1/1/3` |

**STP Error**

<img width="1010" height="148" alt="stp-error" src="https://github.com/user-attachments/assets/0db2a379-35ef-475f-bec9-4198ef88a05a" />

###  ⚠️ Note This error was displayed because I configured DSW1 G1/1/2 - G1/1/3 interface as trunk first and since i haven't configured DSW2 G1/1/2 - G1/1/3 yet that error was displayed That’s expected.

---

## 🔍 Verification (Run on Each Switch)

| What to Check | Command |
|---|---|
| Verify trunks are up | `show interfaces trunk` |
| Verify interface status | `show interfaces status` |

---

## Trunk verification Bellow:

### F1-ASW1

<img width="718" height="132" alt="F1-ASW1-Trunk" src="https://github.com/user-attachments/assets/d2ef3314-0801-439d-ae0a-ed900ce48822" />

### F1-ASW2

<img width="671" height="129" alt="F1-ASW2-Trunk" src="https://github.com/user-attachments/assets/0aea8fab-4eb6-4a79-b042-ee9bbc65068f" />

### F2-ASW1

<img width="674" height="124" alt="F2-ASW1-Trunk" src="https://github.com/user-attachments/assets/54070383-2446-4d23-aa53-e8e8824419a9" />

### F2-ASW2

<img width="690" height="137" alt="F2-ASW2-Trunk" src="https://github.com/user-attachments/assets/829e6d05-9921-404c-bbae-debc1dab59e8" />

### F3-ASW1

<img width="678" height="138" alt="F3-ASW1-Trunk" src="https://github.com/user-attachments/assets/fdee7924-f7a4-4f44-8fd3-f45ab27f69e8" />

### F3-ASW2

<img width="663" height="132" alt="F3-ASW2-Trunk" src="https://github.com/user-attachments/assets/96c740a6-32d2-4a58-ad8d-e0f09626a757" />
