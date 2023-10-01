Amass is another subdomain tool, the drill is to use multiple tools because multiple **tools** is equal to different **results**

We can download `amass` on kali with 

```bash
$ sudo apt install amass
```


## **General Usage**

```bash
# find subdomains of websites
$ amass enum -d <domain>
```

#### **Example**


![](https://i.imgur.com/EtJJxzj.jpg)


**We can also write an automation to do this, this time we will just upgrade the script we used in our last session with `assetfinder`**


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


echo "[+] Harvesting subdomains with Amass..."
amass enum -d $url >> $url/recon/f.txt
sort -u $url >> $url/recon/final.txt
rm $url/recon/f.txt
```