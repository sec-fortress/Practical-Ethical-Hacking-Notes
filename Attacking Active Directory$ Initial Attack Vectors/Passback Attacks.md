A pass-back attack is a printer or IOT type of attack, usually we are looking for something that connect to LDAP or something that does SMB connection. If the attacker has access to a devices embedded web server **(EWS)**, they may be able to discover clear text LDAP or SMTP credentials, which could be passed around.

Or, **even if the credentials are masked**, the attacker can change the LDAP/SMTP server IP address in the EWS and forward a request to a `netcat` listener. Upon doing so, the client device will send clear text credentials to the attackers listener.

### _Resources :_

- [Breaching Active Directory](https://sec-fortress.github.io/posts/articles/posts/Breaching%20Active%20Directory.html) 
- [how-to-hack-through-a-pass-back-attack](https://www.mindpointgroup.com/blog/how-to-hack-through-a-pass-back-attack/)





