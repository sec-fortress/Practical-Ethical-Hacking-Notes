Now that we have important and filtered information gotten from the enumeration process: [[Kiopitrix]]

We can start to check out Vulnerabilities, the first one here is the:
```
mod_ssl/2.8.4 - mod_ssl 2.8.7 and lower are vulnerable to a remote buffer overflow which may allow a remote shell.
```

Which allows a **remote shell** through a remote buffer overflow attack, cool, let Google Search:
***Checklist:***

- [ ] With the keyword `mod ssl 2.8.4 exploit` whereas adding **exploit** gives us some few links; [outdated exploit](https://www.exploit-db.com/exploits/764), [updated exploit](https://github.com/heltonWernik/OpenLuck) 
- [ ] We can also search using the **searchsploit** command in Kali Linux, Note that the more specific you are, the more chances you won't get any results, here is how it is done; 
	- using the command **`searchsploit mod ssl 2.8.4`** gives us this;
	
	```shell
	Exploit Title                                                         |      Path
	
	Apache mod_ssl < 2.8.7 OpenSSL - 'OpenFuck.c' Remote Buffer Overflow  | unix/remote/21671.c
	Apache mod_ssl < 2.8.7 OpenSSL - 'OpenFuckV2.c' Remote Buffer Overflow(1) | unix/remote/764.c
	Apache mod_ssl < 2.8.7 OpenSSL - 'OpenFuckV2.c' Remote Buffer Overflow(2) | unix/remote/47080.c
	
	Shellcodes: No Results
	```

Next up is the:

```sh
SMB Version
 Unix (Samba 2.2.1a)
```

After various research a lot of articles and source point to a **Trans2open Vulnerability** which was disclosed 04/07/2003. We have various exploit on the web including a manual exploit built with C after getting reverse shell as a normal user [the C e](https://github.com/KernelPan1k/trans2open-CVE-2003-0201)