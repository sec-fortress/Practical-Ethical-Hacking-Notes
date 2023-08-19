As usual login with `root:tcm` , do `dhclient` and then `ip a` to get ip address of the target

![](https://i.imgur.com/wNTSRC3.png)

Connect to target via SSH  to make things easier 

![](https://i.imgur.com/TF1sW8Z.png)

Now let start attacking to get root , run your nmap scan with the below command 

```sh
# Nmap 7.94 scan initiated Sat Aug 19 04:02:55 2023 as: nmap -p- -sCV -v --min-rate=1000 -T4 -oN nmap_academy.txt 192.168.0.117
Nmap scan report for dev (192.168.0.117)
Host is up (0.0012s latency).
Not shown: 65526 closed tcp ports (conn-refused)
PORT      STATE SERVICE  VERSION
22/tcp    open  ssh      OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)
| ssh-hostkey: 
|   2048 bd:96:ec:08:2f:b1:ea:06:ca:fc:46:8a:7e:8a:e3:55 (RSA)
|   256 56:32:3b:9f:48:2d:e0:7e:1b:df:20:f8:03:60:56:5e (ECDSA)
|_  256 95:dd:20:ee:6f:01:b6:e1:43:2e:3c:f4:38:03:5b:36 (ED25519)
80/tcp    open  http     Apache httpd 2.4.38 ((Debian))
|_http-server-header: Apache/2.4.38 (Debian)
|_http-title: Bolt - Installation error
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
111/tcp   open  rpcbind  2-4 (RPC #100000)
| rpcinfo: 
|   program version    port/proto  service
|   100000  2,3,4        111/tcp   rpcbind
|   100000  2,3,4        111/udp   rpcbind
|   100000  3,4          111/tcp6  rpcbind
|   100000  3,4          111/udp6  rpcbind
|   100003  3           2049/udp   nfs
|   100003  3           2049/udp6  nfs
|   100003  3,4         2049/tcp   nfs
|   100003  3,4         2049/tcp6  nfs
|   100005  1,2,3      35743/tcp6  mountd
|   100005  1,2,3      39631/tcp   mountd
|   100005  1,2,3      50085/udp6  mountd
|   100005  1,2,3      54481/udp   mountd
|   100021  1,3,4      32775/tcp   nlockmgr
|   100021  1,3,4      38437/udp6  nlockmgr
|   100021  1,3,4      38803/tcp6  nlockmgr
|   100021  1,3,4      42255/udp   nlockmgr
|   100227  3           2049/tcp   nfs_acl
|   100227  3           2049/tcp6  nfs_acl
|   100227  3           2049/udp   nfs_acl
|_  100227  3           2049/udp6  nfs_acl
2049/tcp  open  nfs      3-4 (RPC #100003)
8080/tcp  open  http     Apache httpd 2.4.38 ((Debian))
|_http-server-header: Apache/2.4.38 (Debian)
|_http-title: PHP 7.3.27-1~deb10u1 - phpinfo()
| http-methods: 
|_  Supported Methods: GET HEAD POST OPTIONS
| http-open-proxy: Potentially OPEN proxy.
|_Methods supported:CONNECTION
32775/tcp open  nlockmgr 1-4 (RPC #100021)
39631/tcp open  mountd   1-3 (RPC #100005)
49349/tcp open  mountd   1-3 (RPC #100005)
59539/tcp open  mountd   1-3 (RPC #100005)
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Read data files from: /usr/bin/../share/nmap
Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
# Nmap done at Sat Aug 19 04:03:11 2023 -- 1 IP address (1 host up) scanned in 15.82 seconds
```

We have port 80/HTTP opened, checking it out looks like we've another default web page 

![](https://i.imgur.com/p9KMlEI.png)

Running Directory Bruteforce with `ffuf` we have 6 entries found, let check them out

![](https://i.imgur.com/1acxDub.png)

`/public` is a 301 that leads to a page we don't have access to , `/index.php` takes us back to the default page, down from `/src` to `/extensions` is just an index page , also there is information disclosure of `Apache/2.4.38 (Debian) Server`

![](https://i.imgur.com/TY13A6q.png)

![](https://i.imgur.com/wHlRR1O.png)

![](https://i.imgur.com/GhzSxdY.png)

![](https://i.imgur.com/XH4htVy.png)


Nice soo, let enumerate vulnerabilities for versions of frameworks used on the website , which i don't seem to find anything interesting, remember we also have port 8080/HTTP running, which is a default `phpinfo` page 

![](https://i.imgur.com/uS8i01U.png)

However enumerating the PHP version doesn't seem to be giving, so i did directory Brute force and found 2 entries , `/index.php` takes us back to the default page but `/dev` gives us a successfully installed page of the `bolt` default page that was wrongly configured on port 80/HTTP

![](https://i.imgur.com/RP0rVDT.png)

![](https://i.imgur.com/8bm0ygB.png)

I found a local file inclusion vulnerability but i need to be logged in first , you can read about it from [here](https://www.exploit-db.com/exploits/48411)

![](https://i.imgur.com/EBWrH6W.png)

![](https://i.imgur.com/V16NJhZ.png)

So i decided to create an account and then try it out, the vulnerability existed, **local file inclusion**

![](https://i.imgur.com/UXrqKeV.png)

![](https://i.imgur.com/GnVctnu.png)

The user `/home/jeanpaul` existed , but we need a way to get the password, i can't read `/etc/shadow` , but we still have one more service to enumerate which if `NFS` {Network File Sharing} , i tried out `hydra` too 😅 , but it didn't work <3

![](https://i.imgur.com/LyqCVHj.png)

Let enumerate NFS , you can read on mounting NFS shares from [here](https://jamespatricksec.medium.com/enumerating-and-exploiting-nfs-1571cb484e16) , Tried several passwords but to no avail , right here we can see we have a `note.txt` and an `id_rsa` file

![](https://i.imgur.com/lvZxlZp.png)

I then decided to bruteforce the file and came across a tool called `fcrackzip` , you can install it doing `sudo apt install fcrackzip` on your terminal and run it with `fcrackzip -v -u -D -p /usr/share/wordlists/rockyou.txt save.zip`

![](https://i.imgur.com/42aBeL8.png)

![](https://i.imgur.com/mKzkoYK.png)

Now that it is cracked , i guess we can read the information, i also guess the id_rsa key is for `jeanpaul`

![](https://i.imgur.com/65mBaJZ.png)

