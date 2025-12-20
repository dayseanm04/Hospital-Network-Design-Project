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

# 🏥 Floor 1 – Trunk VLAN Allow Lists

## 🔗 F1-ASW1 ↔ Distribution Switches

| Trunk Link | ASW Interfaces | DSW Interfaces | Allowed VLANs |
|-----------|----------------|----------------|---------------|
| F1-ASW1 → DSW1 | Gi1/0/23–24 | Gi1/0/1–2 | 101, 110, 600 |
| F1-ASW1 → DSW2 | Gi1/0/21–22 | Gi1/0/1–2 | 101, 110, 600 |

---

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

---

### F1-ASW2 show vlan brief

<img width="988" height="247" alt="F1-ASW2-VLAN" src="https://github.com/user-attachments/assets/c30d600b-cd6d-44df-8b5d-046523708fee" />

### F1-ASW1 show interface trunk

<img width="697" height="228" alt="F1-ASW2-trunk-int" src="https://github.com/user-attachments/assets/6dfd992e-8607-49f9-bf20-518ea414859b" />


