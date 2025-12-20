# 🔀 07 – Configure Allowed VLANs on Trunk Links

This task documents which **VLANs are allowed on each trunk link**
between **Access Switches (ASWs)** and **Distribution Switches (DSWs)**.

Only VLANs that are actually used on each access switch are allowed on its
corresponding trunk links.  
This improves **security**, **performance**, and **troubleshooting clarity**.

### Assume you:

- Enter global configuration mode on the switches
- Select the correct trunk interfaces
- Configure the allowed VLAN list

---

# 🏥 Floor 1 – Trunk Allowed VLAN Lists

## 🔗 F1-ASW1 ↔ Distribution Switches

| Trunk Link | ASW Interfaces | DSW Interfaces | Allowed VLANs |
|-----------|----------------|----------------|---------------|
| F1-ASW1 → DSW1 | Gi1/0/23–24 | Gi1/0/1–2 | 101, 110, 600 |
| F1-ASW1 → DSW2 | Gi1/0/21–22 | Gi1/0/1–2 | 101, 110, 600 |


### F1-ASW1 show vlan brief

<img width="924" height="208" alt="F1-ASW1-VLAN" src="https://github.com/user-attachments/assets/0b1c1864-c08c-45f3-97c6-3fb4105fefc5" />

### F1-ASW1 show interface trunk

<img width="730" height="221" alt="F1-ASW1-trunk-int" src="https://github.com/user-attachments/assets/eea8fdfa-f597-432b-b220-168c7a2f49e6" />

Note: I allowed the VLANs configured earlier on F1-ASW1 on these trunk links. Only VLANs on F1-ASW1 can traverse this link

---

## 🔗 F1-ASW2 ↔ Distribution Switches

| Trunk Link | ASW Interfaces | DSW Interfaces | Allowed VLANs |
|-----------|----------------|----------------|---------------|
| F1-ASW2 → DSW1 | Gi1/0/23–24 | Gi1/0/3–4 | 101, 120, 140, 180, 500 |
| F1-ASW2 → DSW2 | Gi1/0/21–22 | Gi1/0/3–4 | 101, 120, 140, 180, 500 |


### F1-ASW2 show vlan brief

<img width="988" height="247" alt="F1-ASW2-VLAN" src="https://github.com/user-attachments/assets/c30d600b-cd6d-44df-8b5d-046523708fee" />

### F1-ASW2 show interface trunk

<img width="697" height="228" alt="F1-ASW2-trunk-int" src="https://github.com/user-attachments/assets/6dfd992e-8607-49f9-bf20-518ea414859b" />

---

# 🏢 Floor 2 – Trunk Allowed VLAN Lists

## 🔗 F2-ASW1 ↔ Distribution Switches

| Trunk Link | ASW Interfaces | DSW Interfaces | Allowed VLANs |
|-----------|----------------|----------------|---------------|
| F2-ASW1 → DSW1 | Gi1/0/23–24 | Gi1/0/5–6 | 200, 210, 220, 500 |
| F2-ASW1 → DSW2 | Gi1/0/21–22 | Gi1/0/5–6 | 200, 210, 220, 500 |

---

### F2-ASW1 show vlan brief

<img width="949" height="245" alt="F2-ASW1-VLAN" src="https://github.com/user-attachments/assets/6e8f68b9-8b78-43be-9080-cbc0dc5ea6a4" />

### F2-ASW1 show interface trunk

<img width="686" height="225" alt="F2-ASW1-trunk-int" src="https://github.com/user-attachments/assets/6ab892c2-3851-4a8d-a1c1-9d3276c9405e" />

## 🔗 F2-ASW2 ↔ Distribution Switches

| Trunk Link | ASW Interfaces | DSW Interfaces | Allowed VLANs |
|-----------|----------------|----------------|---------------|
| F2-ASW2 → DSW1 | Gi1/0/23–24 | Gi1/0/7–8 | 200, 210, 230, 240, 600 |
| F2-ASW2 → DSW2 | Gi1/0/21–22 | Gi1/0/7–8 | 200, 210, 230, 240, 600 |

---

### F2-ASW2 show vlan brief

<img width="1001" height="225" alt="F2-ASW2-VLAN" src="https://github.com/user-attachments/assets/53fb783f-1fcd-42ea-b747-5cabc014a605" />

### F2-ASW2 show interface trunk

<img width="703" height="237" alt="F2-ASW2-trunk-int" src="https://github.com/user-attachments/assets/5460668b-1b40-4296-9bc0-1aa364b69c5c" />

