What we are saying in finding the right module is that we are looking for a DLL or something similar inside of a program that has no memory protection.

### Practicals

- On your windows machine go to your browser and download this [file](https://github.com/corelan/mona/blob/master/mona.py)
- Copy the file to this location `C:\Program Files (x86)\Immunity Inc\Immunity Debugger\PyCommands` and save it
- Now open immunity debugger and attach vulnserver
- On the little command bar down immunity debugger type in `!mona modules` and you should a pop-up with grren text over dark screen