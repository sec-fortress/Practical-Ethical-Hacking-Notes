Which stands for **Link-Local Multicast Name resolution**

![](https://i.imgur.com/U1nwO4A.png)

### How does LLMNR poisoning work ???

LLMNR works by **sending out multicast queries over local networks asking if any specific computers with certain names exist and whether any have responded with their IP addresses when queried by LLMNR**. LLMNR poisoning is a man-in-the-middle (MITM) attack that exploits this protocol

### Steps to Re-Produce

1. We run the `Responder` script to listen to LLMNR queries made by other devices on that network and **performs man-in-the-middle attacks on them** (This could be early in the morning why people are turning on their PC's)

![](https://i.imgur.com/uYKJtur.png)

2. Then we wait for an unexpected event to occur on the client-side

![](https://i.imgur.com/7V1Ux4X.png)

3. Then we should see a password hash come through

![](https://i.imgur.com/JGlqYNy.png)

4. Finally we can grab a tool like `johntheripper` or `hashcat` to crack this hash

![](https://i.imgur.com/zranx24.png)

