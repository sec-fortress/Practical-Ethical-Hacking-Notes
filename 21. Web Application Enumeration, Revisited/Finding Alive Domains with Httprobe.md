Httprobe is a tool we can use to check for alive subdomains gotten from the result of both `assetfinder` and `amass`

We can install this tool on **Kali Linux** with the command `sudo apt install httprobe`

## **General Usage**

We can pipe the output we got from `amass` and `assetfinder` to `httprobe` to get live domains

```bash
$ cat tesla.com/recon/final.txt | httprobe
```


