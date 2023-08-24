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

- We will go back to our immunity debugger and type in this command `!mona `