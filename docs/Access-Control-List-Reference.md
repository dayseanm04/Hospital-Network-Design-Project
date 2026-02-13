## 📋 Access Control List (ACL) Reference Table

This table is used to **track all ACLs configured** in the hospital network, including their purpose, permitted sources, and where they are applied.

| ACL name | Type | Purpose | Permitted Source(s) | Applied On | Direction | Notes |
|-----:|------|---------|---------------------|------------|-----------|-------|
| Allow-SSH | Standard | Restrict SSH access to network devices | IT PC1 (10.50.50.2)<br>IT PC2 (10.50.50.3) | VTY lines on all network devices | Inbound | Used for MGNT security |
| Translate-NAT | Standard | Translate LAN IPs | 1-3 Floor PCs <br/>172.16.1.0/24 <br/>172.16.2.0/24<br/>172.16.3.0/24 | VTY lines on all network devices | Inbound | Used for MGNT security |

