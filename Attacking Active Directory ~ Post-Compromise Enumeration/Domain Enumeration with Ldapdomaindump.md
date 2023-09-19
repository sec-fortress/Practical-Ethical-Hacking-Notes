
## **When to Use?**

If IPv6 is not possible in a network and we do want to compromise an account, well, this tool is a **"TO-GO"** for us.

## **Example Usage**

**Note:** LDAP requires a bind credential -- can be a low-level domain user -- in order to connect to the LDAP service and run queries.

```powershell
# Make a directory and switch to it
$ mkdir marvel.local
$ cd marvel.local

# For help message
$ sudo ldapdomaindump --help 

# standard enumeration using Credentials
# ldaps:// : domain controller IP
# -u : Specific user on the domain
# -p : Password of specific user on the domain
# -o : Output directory, else output will be generated into current folder
$ sudo ldapdomaindump ldaps://192.168.0.149 -u 'MARVEL\fcastle' -p Password1 -o /tmp

# 

```

