# 🔄 Configuration Change Log

## 🗓 Date
Dec 27 2025
## 📍 Layer
 Distribution / Access 

## 🖥 Devices Affected
- DSW1, DSW2, F1-ASW1, F1-ASW2, F2-ASW1, F2-ASW2, F3-ASW1, F3-ASW2

## ⚙️ Configuration Type
EtherChannel

## 📝 Description
I removed the L2 etherchannel connection from the DSWs To The ASWs

## 🎯 Reason
I will configure L3 Etherchannel instead to prevent unnecessary brodacast being sent to the distribution layer

## 🔗 Related Task / Design Doc
[**Configure-LACP-EtherChannel-ASW-DSW-Links.md**](/skip/01-Configure-LACP-EtherChannel-ASW-DSW-Links.md)

[**02-Configure-Allowed-VLANs-On-EtherChannel-ASW-DSW.md**](skip/02-Configure-Allowed-VLANs-On-EtherChannel-ASW-DSW.md)



## ✅ Verification
- Ping tests
- show commands
- Screenshot reference

## 📌 Result
✅ Successful
