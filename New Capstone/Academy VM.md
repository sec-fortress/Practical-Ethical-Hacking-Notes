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

We got the password which is `student` 




