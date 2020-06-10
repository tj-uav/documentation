---
description: Socket communication tutorial
---

# Socket Communication

## Introduction



## About sockets

* Sockets are a stream of data
* Making a connection
  * IP address and port
  * Server is listening for connections \(can have multiple connections per socket\)
  * Client is making a connection \(1 connection per socket\)
* TCP vs. UDP
* Blocking \(which means we have to use threads\)
* How to get IP address
  * ipconfig on Windows, ifconfig on Linux
  * `127.0.0.1` is the loopback address \(points to yourself\)
  * nmap to see other people's IP addresses

## Client and Server basic example

* GitHub link to the example
* Go through the code and explain each line

## Client and Server advanced example

* Example w/ threading
* GitHub link to the example
* Go through the code and explain each line \(don't need to explain lines in the basic example\)

## Common Errors

* Connection timeouts
  * Need to start server before client
  * Check if IP address and port match up
* Hanging on recv
  * Socket isn't sending
  * Usually you have to close ur terminal and reopen
* 
