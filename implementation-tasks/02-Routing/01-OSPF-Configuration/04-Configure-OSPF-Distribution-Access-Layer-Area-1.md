# 🛰️ Configure OSPF Between DSWs and ASWs (Area 1)

**Goal:** Enable **OSPF process 1 (Area 1)** on:
- **DSW1 + DSW2** (all /30 port-channel links to access switches)
- **All ASWs** (their loopbacks + their /30 uplinks to DSW1 + DSW2)
- **Service-ASW** (loopback + uplinks to DSWs + server subnet)

## Rerence Network Diagram

<img width="879" height="397" alt="reference-area" src="https://github.com/user-attachments/assets/6ac5a6f6-dc7b-4142-8983-e5f2868a504b" />

---
