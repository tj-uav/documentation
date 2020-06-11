# Advanced Example

## Client and Server advanced example

For this advanced example, download the python scripts [here](https://github.com/tj-uav/Lectures/tree/master/Tutorials/sockets/advanced). This tutorial will basically go through the code in more detail. This tutorial will assume that you already know the basic stuff from the basic example, and that you know how to use the **threading library**. If you don't know how to use the threading library, you can learn about it [here](https://docs.python.org/3/library/threading.html).

The changes made to the **client** and **server** code are very similar, it basically makes it so that you can send and receive data at the same time using **threading**.

### The receive method

First, we want to be constantly listening to anything that the other person might be sending. This is done with the `continuously_recv` method that we define. This method simply contains a while loop which is always running the socket's `recv` method and printing out any incoming data.

Since we want this to be constantly running in the background, we put it in a **thread** so that it runs in parallel with the rest of our code. The line `recv_thread.daemon = True` means that if the parent thread \(the rest of the code\) dies, then the child thread will also die. This just makes it easier on us since it kills the thread whenever we Ctrl + C instead of hanging.

### Sending data

Since we want to also be able to send data, we use a while True loop that constantly takes input from the user and sends it via the socket. Because the `continuously_recv` method is running in a thread, both the receiving and sending aspect of the socket can be used at the same time without having to worry about blocking.

