As usual start the VM and run this commands

```sh
root@blackpearl:~# dhclient
root@blackpearl:~# ip a (for target ip address)
```

![](https://i.imgur.com/br1awL2.png)

Connect via SSH to make it easier to communicate with targets (Optional)

![](https://i.imgur.com/ndc7jvJ.png)

Running our Nmap scan to probe/discover Network open ports, We have Port 22, 53 and 80 opened.

```sh
# Nmap 7.94 scan initiated Mon Aug 21 08:18:55 2023 as: nmap -p- -sCV -v --min-rate=1000 -T4 -oN nmap.txt 192.168.0.166
Nmap scan report for blackpearl (192.168.0.166)
Host is up (0.0015s latency).
Not shown: 65532 closed tcp ports (conn-refused)
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)
| ssh-hostkey: 
|   2048 66:38:14:50:ae:7d:ab:39:72:bf:41:9c:39:25:1a:0f (RSA)
|   256 a6:2e:77:71:c6:49:6f:d5:73:e9:22:7d:8b:1c:a9:c6 (ECDSA)
|_  256 89:0b:73:c1:53:c8:e1:88:5e:c3:16:de:d1:e5:26:0d (ED25519)
53/tcp open  domain  ISC BIND 9.11.5-P4-5.1+deb10u5 (Debian Linux)
| dns-nsid: 
|_  bind.version: 9.11.5-P4-5.1+deb10u5-Debian
80/tcp open  http    nginx 1.14.2
|_http-title: Welcome to nginx!
| http-methods: 
|_  Supported Methods: GET HEAD
|_http-server-header: nginx/1.14.2
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Read data files from: /usr/bin/../share/nmap
Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
# Nmap done at Mon Aug 21 08:19:17 2023 -- 1 IP address (1 host up) scanned in 22.22 seconds
```

Starting out with port `80/HTTP` , we have an nginx server web page

![](https://i.imgur.com/txWYUi2.png)

Running Directory Brute force gives us a `/secret` page since checking `/robots.txt` doesn't seems to give us leads

![](https://i.imgur.com/NykjLj3.png)

Navigating to `/secret` we are asked to download a file, after downloading we got this message 😂

![](https://i.imgur.com/Yocj6XK.png)

Nice, a quick help, since we have port 53 opened let perform a zone transfer, we can add the target to our `/etc/hosts` file giving it the domain name `blackpearl.tcm`

![](https://i.imgur.com/4Muv2Zk.png)

Trying out zone transfer, Looks like every attempt failed 😭 But navigating back to the website gives us a `phpinfo` page

![](https://i.imgur.com/7jrkrxJ.png)

![](https://i.imgur.com/KM4NvgK.png)

Great !!, Then we can do a directory bruteforce once again on `blackpearl.tcm` this time, not the IP Address

![](https://i.imgur.com/cQNERGJ.png)

Definitely `/index.php` will take us back to the phpinfo page sooo, let check out `/navigate` which we are referred to a login page

![](https://i.imgur.com/Q5emdP0.png)

+ I couldn't login with default Credentials
+ Checking the source code i can see the CMS version

![](https://i.imgur.com/LyQqTDI.png)

Enumerating this version gives an `# (Unauthenticated) Remote Code Execution` , i also did a directory bruteforce just to be sure on `http://blackpearl.tcm/navigate` and got alot of entries, Nothing seems to be giving good vibes except the `/login.php` 

![](https://i.imgur.com/hGci25k.png)

Going back to the `(Unauthenticated) Remote Code Execution` vulnerability, let look further into it in which you can get the exploit from [here](https://github.com/0x4r2/Navigate-CMS-RCE-Unauthenticated-), Also make sure to follow the guidelines on setting up the exploit on the page 

![Getting the reverse shell](https://i.imgur.com/AieTDDY.png)

![stty shell for more stable shell](https://i.imgur.com/XTkLHsd.png)

### Privilege Escalation

as usual, i will transfer Linpeas first for further investigations 😆

![](https://i.imgur.com/c8YrdLl.png)

- First of all we have the user `alek`

![](https://i.imgur.com/uiYfoGc.png)

- We can run `sudo -l` cos' sudo isn't installed on `www-data`
- Checking for `SUID` we have an unusual binary here which is `/usr/bin/php7.3`

![](https://i.imgur.com/QWEleiF.png)

Great `GTFOBINS` has a payload for it to escalate to root using `PHP`, Tweaking my payload to this: `/usr/bin/php7.3 -r "pcntl_exec('/bin/bash', ['-p']);"`

![](https://i.imgur.com/dfwVNWV.png)

