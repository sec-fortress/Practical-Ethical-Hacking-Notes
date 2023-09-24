
## **Overview**


- Tool used to view and steal credentials, generate kerberos tickets and leverage attacks
- Dump credentials stored in memory
- Few more attacks : Credential dumping, Pass-the-Hash, Over-Pass-the-Hash, Pass-the-Ticket, Silver Ticket and Golden Ticket


## **Installation**

- Download the mimikatz file[.zip] from [here](https://github.com/gentilkiwi/mimikatz/releases/download/2.2.0-20220919/mimikatz_trunk.zip) on your kali machine
- Open the zipped file and navigate to the `/x64/` folder
- Transfer all files in this folder to your windows client machine, In our case it is **SPIDERMAN**
	- We can start up a python3 server on our Attacker machine with `python3 -m http.server 80`
	- Then navigate to your windows machine and open up a browser then type in our Attacking machine IP
	- Look for the files and download them (If you have any difficulty turn off your windows Antivirus)

![](https://i.imgur.com/HwRcWdk.png)

- Open up a Command Prompt with **Administrative privileges** on our SPIDERMAN VM and change directory to downloads (Where the Mimikatz file is located at)

![](https://i.imgur.com/QcWQSpt.png)


## **General Usage**

```powershell
# start mimikatz
c:\Users\peterparker\Downloads>mimikatz.exe

# start debug mode for full efficiency
mimikatz # privilege::debug

# List available options
mimikatz # sekurlsa::
```