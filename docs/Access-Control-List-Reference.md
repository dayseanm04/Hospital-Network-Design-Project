## 📋 Access Control List (ACL) Reference Table

This table is used to **track all ACLs configured** in the hospital network, including their purpose, permitted sources, and where they are applied.

| ACL name | Type | Purpose | Applied On | Direction |
|-----:|------|---------|------------|-----------|
| Allow-SSH | Standard | Restrict SSH access to network devices | VTY lines on all network devices | Inbound |
| Translate-NAT | Standard | Translate HS private IPs |Used on HS-EDGE-R1 and 2 NAT Pool | N/A |

