
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


```powe
```