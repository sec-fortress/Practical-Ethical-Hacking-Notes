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

