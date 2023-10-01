In Python, sockets are a fundamental networking concept used for communication between computers over a network. Sockets enable programs to establish connections, send data, and receive data over various network protocols, such as TCP (Transmission Control Protocol) and UDP (User Datagram Protocol). Here's an explanation of sockets in Python:

Socket Creation:

To use sockets in Python, you need to import the `socket` module. You can create a socket object using the `socket.socket()` function, which takes two parameters: the address family (e.g., `socket.AF_INET` for IPv4) and the socket type (e.g., `socket.SOCK_STREAM` for TCP or `socket.SOCK_DGRAM` for UDP). Here's an example:
```python
import socket


# Create a TCP socket
tcp_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)


# Create a UDP socket
udp_socket = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
```

Socket Communication:

Once you have a socket object, you can use various methods to establish connections, send data, and receive data. Here are some commonly used methods:

- `socket.connect(address)`: Establishes a connection to a remote address.
- `socket.bind(address)`: Binds the socket to a specific address and port.
- `socket.listen(backlog)`: Listens for incoming connections on a TCP socket.
- `socket.accept()`: Accepts an incoming connection and returns a new socket object for communication.
- `socket.send(data)`: Sends data over the socket.
- `socket.recv(buffer_size)`: Receives data from the socket.

Here's an example of a basic TCP server that listens for incoming connections:
```python
import socket


# Create a TCP socket
server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)


# Bind the socket to a specific address and port
server_address = ('localhost', 1234)
server_socket.bind(server_address)


# Listen for incoming connections
server_socket.listen(5)


while True:
    # Accept a client connection
    client_socket, client_address = server_socket.accept()


    # Receive and send data
    data = client_socket.recv(1024)
    client_socket.send(b"Received: " + data)


    # Close the client socket
    client_socket.close()
```

Socket programming in Python allows you to create client-server applications, networked applications, and perform various networking tasks. It provides a powerful and flexible way to communicate over networks using different protocols. The `socket` module in Python provides a wide range of functions and methods to handle network communication efficiently.

Here is how it was used in the video, you can spawn a reverse shell with this:
```python
#SOCKETS - Sockets can be used to connect two nodes together.  

#!/bin/python3
import socket

HOST = '127.0.0.1'
PORT = 7777

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM) #af_inet is ipv4, sock stream is a port
s.connect((HOST,PORT))
```