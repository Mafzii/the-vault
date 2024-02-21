### Internet
- The internet is like a wire 
- Each computer has a unique identifier in an IP 
- Computers connect to the internet through an ISP
- Client computers send packets to servers which then process them
- Data is disassembled into packets and these packets are reassembled at the destination
- A client sends packets to the ISP's server. The ISP's server sends the packets to the web server of the desired application.
- Routers direct your packets around the internet.
- A packet has several layers of wrapping which holds IP addresses to track the path of the connection.

### TCP
 - 3 way handshake:
	 - SYN - Client makes a random number `x` and sends it to the server
	 - SYN ACK - Server acknowledges the request and sends back a random number as an ACK packet. The number can be  `x+1` 
	 - ACK - Client increments the random number again and sends it back as an ACK packet
- After the ACK packet is received by the server, data can be shared between the two
### HTTP
- Initiated by setting up a TCP/UDP connection (default port is 80)
- Client sends initial request to set up connection
- 1.1:
	- Persistent connections were implemented, to close the connection a `Connection: close` header was required in the final request
	- Content-Length: header used to indicate where a request would end and where the server can begin processing the next request. This enabled pipelining.
	- Chunked Transfers: content is sent in pieces in the case of dynamic content, content-length for each chunk is sent. When all chunks are sent a chunk of length 0 is sent to indicate the end
- 2:
	- Made to solve the issue of multiple persistent connections needed
	- Goal was to reduce latency by making requests smaller for a performance gain and more secure
	- Binary data sent
	- Multiplexing: Multiple async requests possible on one connection
	- Header Compression