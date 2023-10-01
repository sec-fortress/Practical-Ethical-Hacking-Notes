First of Run the `Vulnserver` with administrative privileges

![](https://i.imgur.com/HA66Nut.png)

Then run `immunity debugger` with administrative privileges also

![](https://i.imgur.com/oPbscrI.png)

On the Menu Bar, Click `File` then `Attach`

![](https://i.imgur.com/O27nn37.png)

Now select `vulnserver` from the drop down list and click `Attach`

![](https://i.imgur.com/XrzkOzH.png)

Once done, you should see a lot of new stuff on the screen, click the `run` icon to start running

![](https://i.imgur.com/jmoMXPz.png)

Now head over to your Kali machine and do `nc -nv 192.168.0.106 9999` to connect to the vulnserver

![](https://i.imgur.com/brqM1H7.png)

If you are having problems (Probably you are using windows in RDP like me) , this should help

![](https://i.imgur.com/DIP4Nfv.png)

Next thing to do, type `EXIT` to exit the session and do `generic_send_tcp`

![](https://i.imgur.com/T68jrTd.png)

Through the syntax , we need a `spike_script` so let make that, Make sure to save it with the `.spk` extension :

```spike
s_readline();
s_string("STATS ");
s_string_variable("0");
```

> In spiking we are literally sending all kinds of different characters to break the program

![](https://i.imgur.com/TkZLdIa.png)

![](https://i.imgur.com/QUWwcct.png)

The next is `TRUN`, the server doesn't seem vulnerable to the `STATS` command, we will use the same spike code but interchange `STATS` for `TRUN` :

```spike
s_readline();
s_string("TRUN ");
s_string_variable("0");
```

![](https://i.imgur.com/DpOAYpB.png)

The output here as we can see, sends sequence of a's and the EIP is what we are gonna take advantage of

![](https://i.imgur.com/MN2j7CY.png)


