
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
$ sudo python3 /usr/bin/ldapdomaindump ldaps://192.168.0.149 -u 'MARVEL\fcastle' -p Password1 -o /tmp
```



We can now see all files that are dumped in our current folder

![](https://i.imgur.com/d0UOqOT.png)


## **Fixing Errors**

```powershell
# If you have the error as shown below

$ sudo ldapdomaindump ldaps://192.168.0.149 -u 'MARVEL\fcastle' -p Password1
[*] Connecting to host...
[*] Binding to host
Traceback (most recent call last):
  File "/usr/local/bin/ldapdomaindump", line 3, in <module>
    ldapdomaindump.main()
  File "/usr/local/lib/python2.7/dist-packages/ldapdomaindump/__init__.py", line 940, in main
--SNIP--

# Do these
$ pip install ldap3 dnspython future
$ pip install --upgrade ldap3==2.5.1
$ sudo python3 /usr/bin/ldapdomaindump ldaps://192.168.0.149 -u 'MARVEL\fcastle' -p Password1
```