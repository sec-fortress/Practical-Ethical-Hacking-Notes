## What is the [Nmap](https://www.geeksforgeeks.org/nmap-command-in-linux-with-examples/) tool? 

Nmap is an open-source network exploring tool. It rapidly scans large networks and gives back various information. The port table is arguably the most useful feature of Nmap as it gives back a tally of available ports and their statuses, whether they are open, closed, or protected (filtered). Along with the port table, Nmap provides DNS information, operating system guesses and MAC addresses, etc.  
First let’s dig in on the major functionality of Nmap, Port scanning.Following are the available port statuses in Nmap.

Always remember to use this syntax in the exams: **`nmap -T4 -p- -A <ip addr>`**

- **Open**: This means that an application on the target end is actively accepting TCP connections, UDP datagrams, or SCTP associations on this port. Open ports are as a hacker as an open vault to a thief.
- **Closed**: Closed ports respond to data requests. However, no application is listening to them. Nmap uses such ports are used by Nmap to determine the OS or scan the provided IP address for live hosting.
- **Filtered**: Nmap cannot determine whether such ports are open or not as they are protected by dedicated firewalls, router rules, etc. Sometimes these ports respond with ICMP error messages to confuse the exploiter.
- **Unfiltered**: These ports are accessible but, Nmap cannot determine whether they are open or closed.This state occurs only for ACK scans.
- **Open | Filtered**: Nmap places a port in this state when it is unable to determine whether the port falls in the open or filtered category.This occurs in scan types when an open port does not respond.
- **Closed | Unfiltered**: Nmap is unable to tell whether the port is closed or unfiltered.This situation occurs in IP ID idle scan.

## Options in Nmap

The basic syntax of Nmap is:
```sh
nmap [scan type] [option] {target specifications}
```

#### Scan types available in Nmap are:

- [**TCP**](https://www.geeksforgeeks.org/what-is-transmission-control-protocol-tcp/) **scan**: Used to check and perform a three-way handshake between sender and target. It is very noisy.
- [**UDP**](https://www.geeksforgeeks.org/user-datagram-protocol-udp/) **scan**: This scan is performed to check whether a UDP port is open on the target system or not. Unlike TCP scan, this does not have a positive acknowledgment response so, it might sometimes give false positive responses. 
- [**SYN**](https://www.geeksforgeeks.org/what-is-syn-scanning/) **scan**: This is another way of a TCP scan; the Nmap itself creates the SYN packet only difference being that Nmap itself creates the SYN packet.
- [**ACK**](https://www.geeksforgeeks.org/what-is-tcp-ack-scanning/) **scan**: Used to determine whether a post is filtered or not.
- **FIN scan**: It is a kind of stealth scan, which send TCP FIN packets rather than SYN requests.
- **NULL scan**: Clears all the connections and clears everything to clean.
- **IDLE scan**: This is the stealthiest scan of Nmap thus far. 

## Commands in Nmap

Let’s discuss various options that could be used according to one’s needs, with Nmap  
1. **Options with scanning techniques:** Nmap provides the following options with scans:

|option|description|
|---|---|
|-sS|TCP syn Port scan|
|-sT|TCP connect port scan|
|-sA|UDP port scan|
|-sU|TCP ACK port scan|

2. **Options related to HOST discovery:** Following list gives options associated with HOST discovery:

|option|description|
|---|---|
|-n|This option disables DNS resolution.|
|-sn|Only discovers hosts on a given network.|
|-Pn|Only scans ports.|
|-PR|Performs _arp_ discovery on a given local network.|

3. **Options for detecting OS and version of running services:** List of options used for detecting OS and versions of running services:

|option|description|
|---|---|
|-A|Performs aggressive scan.|
|-O|Detects the running operating system of attacked machine.|
|-sV|Detects the versions of running services.|

4. **Timing and Performances options:** These options decide the time and performances of the performed scanning.

|option|description|
|---|---|
|-T0|Performs paranoid IDS evasion.|
|-T1|Performs sneaky IDS evasion.|
|-T2|This is used for polite IDE evasion.|
|-T3|This option is the normal IDE evasion.|
|-T4|This performs an aggressive speed scan.|
|-T5|Performs insane speed scans, fastest of all.|

5. **Port specifications:** Options provided with port scanning.

|option|description|
|---|---|
|-p-|Used for scanning all ports on a given network.|
|-p|Used to scan a range of ports.|
|-F|Used for fast port scanning.|

## Example of Nmap scan

Let us use a result of a Nmap scan to understand and interpret that result.The following command was used and its output is saved in a file named nmap_res.txt. 

nmap -T4 -A scanme.nmap.org > nmap_res.txt

The output of this command should be something like this

![Result of a standard Nmap scan](https://media.geeksforgeeks.org/wp-content/uploads/20220910015046/Picture1-660x365.png)

Now, let us go one by one through different parts of the result and understand them. 

![](https://media.geeksforgeeks.org/wp-content/uploads/20220910015659/Picture2-660x139.png)

Here, Nmap tells us that the domain passed as an argument is up and running and returns its IPv4 and IPv6 addresses.  Then, it comes down to PORTs, arguably the most helpful feature of Nmap. It shows upfront that port 22, which is a TCP port is open. It has SSH running and it also gives back the version of OpenSSH used. Now, one could use this data to find various exploits related to this particular version or one could use the SSH keys given back to exploit the given network. Let’s move to the next part.

![](https://media.geeksforgeeks.org/wp-content/uploads/20220910020307/Picture3-660x134.png)

Now, we get more port information such as ports 139, 445, and 514 are filtered. However, ports 80, 9929, and 31337 are open. Now, here port 80 is an HTTP port, which could be exploited as we also get the version of the server it is running on ‘Apache httpd 2.4.7 (Ubuntu)’. One can use any exploit for this version.

![](https://media.geeksforgeeks.org/wp-content/uploads/20220910021030/Picture4-660x106.png)

Here, Nmap gives us guesses of the possible OS running on the backend machine. It gives the probability for the different OS as the target has filtered it from the enumeration.

You can use this few resource to learn more:
- https://tryhackme.com/room/furthernmap
- https://tryhackme.com/room/nmap01
- https://hackersploit.org/nmap-scan-timing-performance/