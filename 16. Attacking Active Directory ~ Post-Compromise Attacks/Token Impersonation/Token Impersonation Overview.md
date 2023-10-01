## **Overview**

Tokens are just like browser cookies in concept, they are temporary keys that allows access to a system/network without having to provide credentials each time we access a file.


## **Types**

**Delegate :** Created for logging in to a machine or Using Remote Desktop.

**Impersonate :** "Non-Interactive" Such as attaching a network drive or a domain logon  script.


## **Finding Tokens**

Ideally, you want to find tokens of a domain administrator in order expose additional attack vectors against the domain controller.

To move laterally across different computers on the domain, you could do this via passing hashes or passwords or users that have privileges across multiple systems; or by compromising additional vulnerable services.

