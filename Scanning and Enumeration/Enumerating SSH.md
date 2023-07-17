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

*Errors:*
- In the first error, we where told to specify a **key exchange method**, we can do that by adding **`-oKexMethods=+`** followed by the offers given
- The second error state that we need a particular **host key**, we can specify that with the **`-c`** option followed by the offers given again
- Still we can't connect, just get the approach that this is correct but somehow we are not connecting

*Note:*
> The purpose is not to connect to the machine but to see if we can get any banners that might expose sensitive information to us, once we have those information or whether you have them not, **`ctrl+c`** should be done in your terminal if enumeration is still in progress