Assetfinder is a subdomain enumeration tool made by [tomnomnom](https://github.com/tomnomnom/assetfinder) used to find domains and subdomains potentially related to a given domain.
## **Installation**

```shell
# Install assetfinder with default apt package manager
$ sudo apt install assetfinder
```


## **General Usage**

```
# find subdomains related and partially related to a particular domain given
$ assetfinder <domain name>

# saved gather subdomains into a TXT file
$ assetfinder <domain name> >> subd.txt
```

#### **Example**


![](https://i.imgur.com/m7u0vei.png)



## **Automating Assetfinder Scan with Bash**


We don't want partially relative subdomains from assetfinder output, we only want domains related to the original domain