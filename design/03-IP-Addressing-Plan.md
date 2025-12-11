# 🌐 03 – IP Addressing Plan

For this IP addressing plan I will use **VLSM (Variable Length Subnet Masking)** to allocate the right number of IP addresses to each hospital department.
<br/>
Each floor uses a separate **/24 network**

---

# 🧩 Floor 1 – IP Addressing (172.16.1.0/24)

| Department | Subnet | Mask | Usable IP Range | Devices |
|-----------|--------|------|------------------|---------|
| Emergency Department (ED) | 172.16.1.0/26 | 255.255.255.192 | .1 – .62 | 37 |
| X-Ray / Imaging | 172.16.1.64/27 | 255.255.255.224 | .65 – .94 | 11 |
| Hospital Security/Safety Office | 172.16.1.96/28 | 255.255.255.240 | .97 – .110 | 8 |
