---
description: Basic socket communication example in Python
---

# Basic Example

## Client and Server basic example

For this basic example, download the python scripts [here](https://github.com/tj-uav/Lectures/tree/master/Tutorials/sockets/basic). This tutorial will basically go through the code in more detail.

### Server code

The first few lines are used to create the socket object. `socket.AF_INET` means that it communicates over WiFi, and `socket.SOCK_STREAM` means that it's a _TCP_ socket.

The next few lines make the actual connection. `sock.bind((IP, PORT))` binds the socket to that IP and port. This means that any connections going to this socket will be made to that IP and port. `sock.listen(1)` means that it'll listen for 1 connection, and `conn, addr = sock.accept()` actually makes the connection.

The function `conn.receive(1024)`is used to receive data from the client. The 1024 in this example is the **buffer**, which is the max number of **bytes** that the connection will read at a time. The reason we use the `decode()` function is because the `conn.receive` function returns a **bytes** object, and `.decode` converts that to a **string**.

Finally, to send data, we first convert our string that we wanna send to bytes using `sending_data.encode()`, and then send that data using the function `conn.send`. After we're done using the socket, we run `conn.close()` to close that individual connection and `sock.close()` to close all socket connections.

### Client code

The **client** code is pretty much the same except for a couple of differences. First, while the **server** code could create multiple connections w/ one socket and used the `conn` object to represent each connection, the **client** code only makes one connection per socket and uses the `sock` object for everything.

Additionally, the process of making the actual connection part is different. Instead of **binding** itself to an IP and port and listening for others to connect to it, the **client** side makes the actual connection using the `sock.connect` function.

**NOTE:** The IP address and port in both the server code and the client code MUST be the same, and the IP should be the IP of the server.

