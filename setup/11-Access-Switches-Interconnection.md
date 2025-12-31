# 🔗 Access Switches Interconnection

## 📌 Purpose
This document describes the **interconnections between Access Switches (ASWs)** in the hospital network.  
These links provide **redundancy and Layer 2 connectivity** between access layer switches on the same floor.

## Refernce Netork Diagram

<img width="551" height="147" alt="reference-network-diagram" src="https://github.com/user-attachments/assets/530bc025-1921-4b91-89a4-ce4868f8dffb" />

---

## 🏥 Access Layer Interconnection Overview

- Access switches are interconnected **per floor**
- Each floor has **two access switches**
- Inter-switch links are **Layer 2**
- These links support:
  - Redundancy
  - Faster convergence with STP

---

## 🔌 Physical Connection Table

### 🏢 Floor 1 Access Switches
| From Device | Interface | To Device | Interface |
|---|---|---|---|
| F1-ASW1 | G1/1/1 | F1-ASW2 | G1/1/1 |
| F1-ASW1 | G1/1/2 | F1-ASW2 | G1/1/2 |

---

### 🏢 Floor 2 Access Switches
| From Device | Interface | To Device | Interface |
|---|---|---|---|
| F2-ASW1 | G1/1/1 | F2-ASW2 | G1/1/1 |
| F2-ASW1 | G1/1/2 | F2-ASW2 | G1/1/2 |

---

### 🏢 Floor 3 Access Switches
| From Device | Interface | To Device | Interface |
|---|---|---|---|
| F3-ASW1 | G1/1/1 | F3-ASW2 | G1/1/1 |
| F3-ASW1 | G1/1/2 | F3-ASW2 | G1/1/2 |

---

## ✅ Next: [Configure Layer 2 EtherChannel ASWs interconnections](/implementation-tasks/01-Redundancy/04-Configure-L2-LACP-EtherChannel-Between-Access-Switches.md)

