# 📞 VoIP Deployment Overview.md

## 📌 Overview

This document explains how **VoIP devices (IP phones)** are connected to the network, how they interact with **PCs and access switches**, and the **naming standards** used for VoIP devices.

The goal is to ensure **consistent deployment** and **clear identification** across the network.

## Reference Network Diagram

<img width="514" height="438" alt="reference-topology" src="https://github.com/user-attachments/assets/d49c82cd-7325-459e-83a7-4130975aaf2b" />

---

## 🔌 VoIP Physical Connection Layout

Each VoIP phone acts as a **pass-through device** between the PC and the switch.

### 📡 Connection Flow

- PC → VoIP Phone (PC Port)
- VoIP Phone (Switch Port) → Access Switch

### 🧠 How It Works

- The **VoIP phone** connects directly to the **Access Switch**
- The **PC** connects to the **PC port** on the VoIP phone
- The phone tags voice traffic using the **Voice VLAN**
- The PC continues to use the **Data VLAN**

This setup allows **one switch port** to support **both voice and data traffic**.

---

## 🏷️ VoIP Device Naming Standard

To keep devices easy to identify, I used a **consistent naming convention**.

### 📛 Naming Format 

**`<Department>-V<Number>`**

### 🧪 Example
- `ED-1` → Emergency Department PC 1  
- `ED-V1` → Emergency Department **VoIP Phone 1**

This standard helps with:
- Troubleshooting
- Inventory tracking
- Network documentation

### ✅ Click here for the VOIP VLAN Design [Click here for the VOIP VLAN Design](/design/06-Voice-VLAN-Design.md)

