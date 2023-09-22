
Kerberoasting is a very popular and quick way to get domain admin in a network, The attack takes advantage of service accounts.

The attacker uses a known username and password of a user on a domain.

**A typical Kerberos workflow is:**

- Once a user logs into a domain-joined system, they get a TGT (ticket-granting ticket).
- Then, they'll use that TGT to request a TGS (ticket-granting service) ticket any time they need to authenticate to a service.
- The TGS is then passed to an application server on the network for authentication.

Any domain user can request a TGS. This is because:

- **The domain controller does not determine if a user can access a network service**.
- It simply provides a ticket to forward to a service and **expects the service to determine permissions**.

The important part here is:

- A TGS **contains a service principal's password hash**.
- **Service principals are service accounts** that run daemons on a server.

Kerberoasting works by requesting TGS, but:

- **The attacker does not forward the TGS to the server.**
- Rather, the attacker collects the Kerberos TGS hash and attempts to crack it to reveal a service principal's cleartext password.

![](https://i.imgur.com/vyxKu8q.png)

