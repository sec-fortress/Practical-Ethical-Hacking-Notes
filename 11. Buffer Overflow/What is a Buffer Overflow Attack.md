Attackers exploit buffer overflow issues by overwriting the memory of an application. This changes the execution path of the program, triggering a response that damages files or exposes private information. For example, an attacker may introduce extra code, sending new instructions to the application to gain access to IT systems.

If attackers know the memory layout of a program, they can intentionally feed input that the buffer cannot store, and overwrite areas that hold executable code, replacing it with their own code. For example, an attacker can overwrite a pointer (an object that points to another area in memory) and point it to an exploit payload, to gain control over the program.

### Quick Visual Recap

- In the Stack we are overflowing the buffer space to reach the **EIP**
- We can use the **EIP** to point into directions that we instruct

https://github.com/encryptedninja/command-center/raw/master/buffer_overflow/images/
### Steps to Conduct a Buffer Overflow Attack

- [ ] Spiking
- [ ] Fuzzing
- [ ] Finding the offset
- [ ] Overwriting the EIP
- [ ] Finding bad characters
- [ ] Finding the right module
- [ ] Generating Shellcode
- [ ] Root!!

### Getting Started

- Make sure you have a Windows operating system (windows 10 Preferably)
- Download immunity Debugger from [here](https://debugger.immunityinc.com/ID_register.py) , then download the vulnserver from [here](https://github.com/stephenbradshaw/vulnserver) (Make sure it is the complete zipped file) 
- Now install immunity debugger, Note : you might be asked to install python2 so click "yes" or "accept"
- Now we are ready