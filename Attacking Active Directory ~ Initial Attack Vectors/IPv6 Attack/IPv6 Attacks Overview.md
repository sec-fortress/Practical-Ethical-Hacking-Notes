If both the IPv4 and IPv6 is turned on and if you are utilizing IPv4 then who’s doing DNS for IPv6, the simple answer is usually nobody.

Now we will setup an attacker machine that will listen to IPv6 and represent itself as a DNS for it.

![](https://i.imgur.com/skmtiZ1.png)

When we reboot the machine then a machine that reboot will triggers an event that event comes through to us. We can use that machine to login to the Domain Controller and it does not have to be an admin or anything and we can get information, a lot of information out of just that we can potentially use that machine to create another machine.

We can wait for somebody to maybe login to the network or use their credentials somewhere and it will comes to us in the form of NTLM just like Responder, SMB relay.

We relay this, we do what’s called LDAP relaying. We LDAP relay over to the Domain Controller with this NTLM credentials, we log in if it’s a domain administrator to the domain controller.

Guess what, We created an account. It creates an account for us.

>The tool we’re going to use is called Man in the Middle 6(MITM6).

This is one of the most Fun attack and still very undetected.

