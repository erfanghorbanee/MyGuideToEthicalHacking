# Socket

A socket in computer networking is essentially a way to connect two nodes on a network to communicate with each other. Think of it like an electrical socket; it provides an endpoint for devices to connect to electricity. Similarly, a networking socket is an endpoint for sending and receiving data across a network.

## Practical Example: Web Browsing

Let's use a practical example of visiting a website:

1. **Opening a Socket**:

    - When you type `www.example.com` into your web browser and press Enter, your computer opens a socket to connect to the server hosting `example.com`.
2. **Connection Over IP**:

    - Your computer uses the Internet Protocol (IP) to find out the IP address of `www.example.com`. Let's say it's `93.184.216.34`.
3. **Establishing a TCP Connection**:

    - Your computer then sets up a TCP connection to the server at `93.184.216.34` through the socket. TCP ensures that the data sent and received is reliable and arrives in order.
4. **Sending a Request**:

    - Once the connection is established, your browser sends a request through the socket asking for the homepage of `example.com`.
5. **Receiving the Response**:

    - The server at `example.com` sends the webpage data back through the socket to your browser.
6. **Closing the Socket**:

    - After the webpage is fully loaded, the socket may be closed, ending the communication unless kept open for further data exchange, like when a page automatically updates information.

## Why Sockets Are Useful

Sockets abstract the complex details of network communication. Without sockets, developers would have to deal directly with network protocols at a much lower level (e.g., handling individual packets, managing network errors, establishing and maintaining connection states). With sockets, this complexity is hidden, and developers can use simple commands to send and receive data.

Sockets can work with different types of network protocols, but the most common are TCP (reliable, connection-oriented) and UDP (unreliable, connectionless). They are used not just for web browsing but also for various other applications like email, streaming videos, or connecting IoT devices.
