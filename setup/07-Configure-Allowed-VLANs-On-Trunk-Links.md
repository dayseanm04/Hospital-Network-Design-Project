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

