
**_Here are explanations and examples of the commands:_**

`ip a`:

- - Explanation: Displays the network interfaces and their associated IP addresses.
    - Example: Running `ip a` would show information about network interfaces, including their IP addresses, MAC addresses, and other details.

`ifconfig`:

- - Explanation: Displays the configuration and status of network interfaces.
    - Example: Running `ifconfig` would show the configuration details, including IP addresses, MAC addresses, and other information for active network interfaces.

`iwconfig`:

- - Explanation: Displays the configuration and status of wireless network interfaces.
    - Example: Running `iwconfig` would show the configuration details, such as wireless signal strength, frequency, and encryption information, for active wireless interfaces.

`ip n`:

- - Explanation: Displays the Neighbor Table, which contains the IP-to-MAC address mappings for devices in the local network.
    - Example: Running `ip n` would show the IP and MAC addresses of devices that have recently communicated with the current device.

`arp -a`:

- - Explanation: Displays the ARP (Address Resolution Protocol) cache, which maps IP addresses to MAC addresses.
    - Example: Running `arp -a` would show the IP and MAC addresses of devices that have been resolved recently by the ARP protocol.

`ip r`:

- - Explanation: Displays the routing table, which contains information about network routes.
    - Example: Running `ip r` would show the routing table, including destination networks, gateway IP addresses, and network interfaces.

`route`:

- - Explanation: Displays or manipulates the IP routing table.
    - Example: Running `route` would display the routing table, similar to the `ip r` command.

`ping`:

- - Explanation: Sends ICMP echo requests to a specified IP address to check network connectivity and measure round-trip time.
    - Example: Running `ping 8.8.8.8` would send ICMP echo requests to the IP address "8.8.8.8" (Google's DNS server) and display the round-trip time and packet loss statistics.

These commands are commonly used for network troubleshooting, configuration, and gathering network-related information in Linux systems.