An SMB relay attack **allows us to relay SMB authentication requests to another host, gaining access to an authenticated SMB session if the user has access and network logins are allowed on the target host**. If the user has administrator access in the target host, it is possible to execute arbitrary commands.

![](https://i.imgur.com/uxIHt98.png)

### How does this Attack work

First of all we need to be sure that that SMB signing is disabled, we can do this by using nmap as shown below

![](https://i.imgur.com/OjIsj29.png)

We want to turn off the **SMB** and **HTTP** option form the `responder.conf` file because we wanna make sure, this hashes are not just been captured, but they are relayed also

![](https://i.imgur.com/V6D6sNt.png)

We can now run `responder` alongside another tool called `ntlmrelayx` which is responsible for the "message signing disabled" prompt we got from nmap, Also this will dump the hashes from the windows **SAM** file

![](https://i.imgur.com/YXuUKHP.png)
![](https://i.imgur.com/gQakMYk.png)

We still need client interaction and as usual we can do that with `\\ATTACKER-IP`

![](https://i.imgur.com/7V1Ux4X.png)

We can also get a reverse shell with `ntlmrelayx` by adding the `-i` option to our command

![](https://i.imgur.com/aZt0dcQ.png)

We can then start up our listener and our shell would look like this 

![](https://i.imgur.com/jEaBAGM.png)

We can also run system commands with the `-c` option using `ntlmrelayx` , as shown below the whoami command tells us we are **nt authority\system**

![](https://i.imgur.com/jUg42xH.png)
