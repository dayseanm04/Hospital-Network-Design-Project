# 🖥️ Configure DHCP SRV IP address.md

**Goal:** Assign a **static IP address** for **DHCP-SRV** in the **Servers VLAN (VLAN 700)** and verify connectivity to the gateway.

## Reference network Diagram

<img width="483" height="147" alt="reference-net-diagram" src="https://github.com/user-attachments/assets/a26ec6e8-5e91-4bd5-bec0-cd67ca246e14" />

## 🌐 Network Info (VLAN 700 — Servers)

| Item | Value |
|---|---|
| VLAN | **700 (Servers VLAN)**|
| VLAN 700 SVI (Gateway) | **10.10.10.1 /27** |
| Subnet Mask | **255.255.255.224**  |
| DHCP-SRV Static IP | **10.10.10.2** |


---

## 🛠️ Step-by-Step (Cisco Packet Tracer Server)

### 1️⃣ Open the DHCP-SRV device
- Click **DHCP-SRV**

### 2️⃣ Go to the IP configuration screen
- Click **Desktop**
- Click **IP Configuration**

### 3️⃣ Configure the static IP settings

#### ♦️ Enter the following:

| Field | Value |
|---|---|
| IP Address | **10.10.10.2** |
| Subnet Mask | **255.255.255.224** |
| Default Gateway | **10.10.10.1** ✅  |

---

## ✅ Verification 

### 4️⃣ Open Command Prompt on the server
- Click **Desktop**
- Click **Command Prompt**

### 5️⃣ View DHCP-SRV ipconfig

Run:
- `ipconfig` 

<img width="739" height="324" alt="DHCP-ipconfig" src="https://github.com/user-attachments/assets/f0895b17-3086-4dc8-a543-f1cd05ddc2b0" />
