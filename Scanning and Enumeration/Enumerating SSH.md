## What is SSH
**SSH**, or Secure Shell, is a protocol used to securely log onto remote systems. It is the most common way to access remote Linux servers.

## Enumeration
```sh
┌──(sec-fortress㉿kali)-[~/kioptrix]
└─$ ssh 172.16.216.130             
Unable to negotiate with 172.16.216.130 port 22: no matching key exchange method found. Their offer: diffie-hellman-group-exchange-sha1,diffie-hellman-group1-sha1

┌──(sec-fortress㉿kali)-[~/kioptrix]
└─$ ssh 172.16.216.130 -oKexAlgorithms=+diffie-hellman-group-exchange-sha1              
Unable to negotiate with 172.16.216.130 port 22: no matching host key type found. Their offer: ssh-rsa,ssh-dss

┌──(sec-fortress㉿kali)-[~/kioptrix]
└─$ ssh -oKexAlgorithms=+diffie-hellman-group1-sha1 -c ssh-rsa 172.16.216.130
Unknown cipher type 'ssh-rsa'
```