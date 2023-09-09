First of all on the attacking machine start your responder listener with the command below {You can run `sudo responder --help` to see what each and every switch does} :

```shell
sudo responder -I wlan0 -dwPv
```

![](https://i.imgur.com/5W0zCBS.png)

Since we need **Client-side** interactions

- Navigate to our **THEPUNISHER** VM
- Login as an **other user** with the username and password `fcastle:Password1`
- Navigate to **File explorer** and do this :

![](https://i.imgur.com/5rCINLz.png)

- Going back to our attacker terminal, we now have the weak **NTLMv2** password hash

![](https://i.imgur.com/UfyvbVb.png)


