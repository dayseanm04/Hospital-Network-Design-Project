# 🔗 03 – Configure L3 LACP EtherChannel between DSW1 ↔ DSW2

In this task I will configure a **Layer 3 (routed) LACP EtherChannel**
between **DSW1** and **DSW2**.

## Rererence Diagram

<img width="620" height="233" alt="implement-l3-LACP" src="https://github.com/user-attachments/assets/05665561-547b-40e2-982b-bc594b839fb5" />

#### ✅ Why L3 EtherChannel here?
- Keeps the inter-distribution link **routed** (no VLANs carried)
- Reduces STP complexity since its a routed port
- Provides **redundancy + bandwidth** using LACP

