# TCP, UDP, and 3-Way Handshake

## TCP vs UDP

![IMAGE 2023-11-01 14:52:42.jpg](../../_resources/IMAGE%202023-11-01%2014_52_42.jpg)

![IMAGE 2023-11-01 14:52:45.jpg](../../_resources/IMAGE%202023-11-01%2014_52_45.jpg)

## TCP 3-Way Handshake Process

This could also be seen as a way of how TCP connection is established. Before getting into the details, let us look at some basics. TCP stands for Transmission Control Protocol which indicates that it does something to control the transmission of the data in a reliable way.

The process of communication between devices over the internet happens according to the current TCP/IP suite model(stripped out version of OSI reference model). The Application layer is a top pile of a stack of TCP/IP models from where network referenced applications like web browsers on the client-side establish a connection with the server. From the application layer, the information is transferred to the transport layer where our topic comes into the picture. The two important protocols of this layer are – TCP, UDP(User Datagram Protocol) out of which TCP is prevalent(since it provides reliability for the connection established). However, you can find an application of UDP in querying the DNS server to get the binary equivalent of the Domain Name used for the website.

![1bb4b3e15d7cec32fb6a4b12440650bb.png](../../_resources/1bb4b3e15d7cec32fb6a4b12440650bb.png)

- Step 1 (SYN): In the first step, the client wants to establish a connection with a server, so it sends a segment with SYN(Synchronize Sequence Number) which informs the server that the client is likely to start communication and with what sequence number it starts segments with
- Step 2 (SYN + ACK): Server responds to the client request with SYN-ACK signal bits set. Acknowledgement(ACK) signifies the response of the segment it received and SYN signifies with what sequence number it is likely to start the segments with
- Step 3 (ACK): In the final part client acknowledges the response of the server and they both establish a reliable connection with which they will start the actual data transfer

&nbsp;

## Evolution of HTTP connections over TCP

1. **Originally HTTP Connections mapped on TCP Connections**: Initially, HTTP (Hypertext Transfer Protocol) used TCP (Transmission Control Protocol) to establish a new connection for each HTTP request and response cycle. This approach was straightforward but inefficient because each new connection requires a fresh setup, which consumes time and resources.

2. **Then evolution to HTTP Persistent Connections with Sequential Requests mapped on TCP Connections**: As an improvement, HTTP introduced the concept of persistent connections (also known as HTTP keep-alive). This change allowed multiple HTTP requests and responses to be sent over a single TCP connection without needing to re-establish a new connection for each request. This sequential mapping of requests optimizes the use of TCP connections.

3. **Benefits**:
   - **Save TCP 3-way handshaking**: TCP connections usually start with a three-way handshake (SYN, SYN-ACK, ACK) to establish a connection. By using persistent connections, HTTP reduces the need to perform this handshake repeatedly for each request, thus saving time and reducing latency.
   - **Save TCP Congestion Control Slow-Start**: The TCP slow-start mechanism is designed to avoid network congestion by gradually increasing the rate of data transmission until it finds the network's capacity. Persistent connections avoid restarting this slow-start process with each new HTTP request, maintaining a more consistent and optimal data flow rate.

4. **Evolution to Persistent Connections with Pipelined Requests mapped on TCP Connections**: Further evolution led to the use of pipelined requests over persistent TCP connections. Pipelining allows multiple HTTP requests to be sent out in a sequence before the first response is received. This can improve throughput and server efficiency, as the server can process multiple requests in parallel, and responses can be prepared and queued in the pipeline.

5. **Improve Server performance thanks to parallelization**: This line highlights the overall benefit of these evolutions — enhancing server performance. By using persistent and pipelined connections, servers can handle requests more efficiently through parallel processing of requests and responses, significantly improving response times and reducing resource usage.
