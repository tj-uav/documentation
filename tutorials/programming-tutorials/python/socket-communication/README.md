---
description: Socket communication tutorial
---

# Socket Communication

## Introduction

We use TCP sockets \(similar to websockets\) a lot in programming for communication. They're used to communicate between the GS and the Jetson via the Bullet, and between the GS computers themselves. Sockets are basically the simplest form of communication over WiFi / Ethernet.

## About sockets

This section is an overview about how sockets actually work. It doesn't contain any code or have anything to do w/ python, but it's nice to know how something works before you use it. If you don't care about that then just skip this part.

### Sockets are a Stream

Sockets work by sending a **stream** of data, which can be thought of as a queue. For example, if device A sends "HELLO", its basically sending "H", then "E", then "L", then "L", then "O." Device B would receive it in the same order \(just like a queue\), so it would receive "H", then "E", then "L", then "L", then "O". Often times, the device can specify how many **bytes** \(characters\) it wants to receive, so if it only wanted to receive 3 characters, it would receive "HEL". Next time when it tried to receive 2 characters, it would receive "LO". This count of how many **bytes** the device wants to receive is called the **buffer**.

### Socket protocols

Most of the time you will be using _TCP_ sockets over an _internet_ connection. There are 2 major socket protocols: _TCP_ and _UDP_. _TCP_ sockets are slightly slower, but more secure as they use something called a **handshake**, whereas _UDP_ sockets are faster but less reliable. For example, when live streaming, you would use _UDP_ sockets since 100% data throughput is not needed. For our purposes however, _TCP_ is the way to go.

Something else that you should know is that sockets are a form of communication over the network layer. There's this thing called the **OSI model** which is the different layers that computers have, but that's a complicated cybersecurity lecture for another day. Just know that sockets communicate over the network layer, which means that they use **IP addresses** to make connections and send data over WiFi routers.

### Making a connection

So how does a socket connection work? Socket connections are based on two things: **IP address and port**. Every time you connected to a WiFi router, the router assigns you an **IP address**, which is basically it's way of identifying you. If you're on windows, go to your terminal and type `ipconfig` to find your **IP address** \(the command is `ifconfig` on Mac and Linux\). If you wanna test your WiFi communication, you can find another computer connected to your WiFi, get it's **IP address**, and run `ping <other computer's ip`. If you wanna be a hackerman and see the IP addresses of other's on your network, download [nmap](https://nmap.org/download.html), go to it in terminal, and type `nmap -sn 192.168.?.*`, where the `?` is the third number in your IP address. This will basically find all other IP address on your network that have the same starting 3 numbers in their IP address as you. 

The other aspect is the **port**. Your computer basically has a bunch of **ports** that it's making connections on; think of it as your computer being the room that you're in, your **IP address** being your room number \(so that people can identify you\), and the **port** being a bunch of doors that connect your room to other rooms.

So now that you know how **IP addresses** and **ports** work, what is a socket connection? A socket connection is used to connect either a **server** with a **client**, or a **server** with multiple **clients**. For example when you go to [google.com](https://www.google.com/), you \(the client\) are making a connection w/ google.com \(the server\). That connection uses a websocket, which isn't the same but is very similar to a TCP socket. For our ground station, the central GS computer will be the **server**, and all the other GS computers, as well as the Jetson, will be the **clients**.

If you want to make a connection to yourself \(for example, testing socket code locally\), you will often use the **loopback address** \(`127.0.0.1`\). This address is called the **loopback address** because it points your computer to yourself, so you make the connection with yourself.

### Sockets are blocking :\(

The final important thing that you need to know about sockets before you get coding is that sockets are **blocking**. To understand this, we need to understand how **threading** works. When python \(or any software\) runs a program, it runs it in one **thread**. This means that it runs it line by line, and it doesn't execute the next line until the current line is finished. The problem with sockets is that they're blocking, which means that if you're trying to receive data using a socket, the program will hang until it receives the data. This means that if we wanna execute other functions while using sockets, we will have to use python's **threading** library.

## Common Errors

#### Connection Timeouts

Connection timeouts happen when you try connecting to a socket through the client, but the server is not listening for connections on the socket. **REMEMBER:** you must always run the server code \(which should be listening for and accepting connections\) before running the client code. The error probably looks something like this: `ConnectionRefusedError: [WinError 10061] No connection could be made because the target machine actively refused it`

To fix this, simply start the server before running the client. Also, make sure that the IP address and port match up in both the server code and the client code.

#### Hanging on the recv\(\) method

If your program is hanging on the recv\(\) method, then it's basically waiting for data to come, and it won't do anything until data comes. Often times, you won't be able to Ctrl + C your program, and you'll have to close the terminal and reopen it to kill your program. To fix this, make sure that the other side of the socket is sending data whenever you're receiving data. Also if you're using a thread, make sure to set `thread.daemon = True` when creating the thread so that you can Ctrl + C the program.

