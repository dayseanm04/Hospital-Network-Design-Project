# 🌍 Configure ISP1-R1 to Use INET-DNS-SRV

## 📌 Overview

In this task, I will configure ISP1-R1 to use the INET DNS Server for domain name resolution. DNS Server IP: 10.20.20.10

## Reference Topology

<img width="835" height="325" alt="toplogy" src="https://github.com/user-attachments/assets/fb3d5afb-915a-4c7e-b5b0-c7f570012f61" />

## 🎯 Objective
- Configure ISP1-R1 to use the INET-DNS-SRV
- Configure domain name for ISP1-R1
- Verify DNS configuration


## 🔧 Configuration on ISP1-R1

On ISP1-R1, Configure domain name:

```bash
ip domain-name ISP1.com
```

Configure DNS name:

```bash
ip name-server 10.20.20.10
```

## 🔍 Verification

#### On ISP1-R1 show hosts

<img width="741" height="226" alt="ISP1" src="https://github.com/user-attachments/assets/469bf88d-50a5-493e-b566-3ecad9ac4039" />


