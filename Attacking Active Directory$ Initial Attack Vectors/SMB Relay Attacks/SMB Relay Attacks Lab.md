
First of all we need to run our nmap scan, to check for the host with **SMB** signing disabled

![](https://i.imgur.com/MlaVrME.jpg)

Now we can save  the host that have the prompt **"message signing enabled but not required"** into a **targets.txt** file

![](https://i.imgur.com/vNu7Yc1.png)

Now we can disable the **HTTP** and **SMB** protocol in the responder.conf file, located under `/etc/responder/Responder.conf`

![](https://i.imgur.com/7mRX0rr.png)

We can then startup `responder` with the syntax used previously in **LLMNR Poisoning** `sudo responder -i wlan0 -dwPv` (v for verbose)

