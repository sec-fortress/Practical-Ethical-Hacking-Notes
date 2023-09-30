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


We don't want partially relative subdomains from assetfinder output, we only want domains related to the original domain, we can use this bash code to do this :

```bash
#!/bin/bash

url=$1

if [ ! -d "$url" ];then
	mkdir $url
fi

if [ ! -d "$url/recon" ];then
	mkdir $url/recon
fi

echo "[+] Harvesting subdomains with assetfinder..."
assetfinder $url >> $url/recon/assets.txt
cat $url/recon/assets.txt | grep $1 >> $url/recon/final.txt
rm $url/recon/assets.txt
```

You can then grant it executable permissions then run it and you should get the target specified as the folder name where subdomain will be saved

#### **Example**

![Uploading file...cnclw]()


