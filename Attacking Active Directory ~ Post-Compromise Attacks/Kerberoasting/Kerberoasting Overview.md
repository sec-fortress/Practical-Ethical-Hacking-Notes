
Kerberoasting is a very popular and quick way to get domain admin in a network, The attack takes advantage of service accounts.


![](https://i.imgur.com/vyxKu8q.png)


Over here what we need to worry about is step 4 which gives us a TGS server's account hash with a tool called `GetUserSPNs.py`.


![](https://i.imgur.com/PJrupO6.png)

we can then copy this hash and attempt to crack it with `john` or `hashcat`

![](https://i.imgur.com/hB2tpx0.png)

