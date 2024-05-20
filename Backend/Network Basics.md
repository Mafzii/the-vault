---
tags:
  - network
---
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
	- Another goal was to reduce latency by making requests smaller for a performance gain and more secure
	- Binary data sent
	- Multiplexing: Multiple async requests possible on one connection
	- Header Compression
	- Frames and Streams: 
		- All HTTP/2 messaged are made up of frames
		- HEADER frame includes metadata
		- DATA frame includes the payload
		- Each request or response has a unique stream ID and is divided into frames
		- A collection of frames is a stream
	- Multiplexing:
		- Frames and Streams allow for asynchronous connections
		- Multiplexing is when multiple requests are sent and they are processed asynchronously 
		- Response is also asynchronous and stream ids are used to see which packet belongs to which request id
	- Header Compression:
		- Sending header details in plain-text each request would bloat request size slowing down connections
		- Headers are also compressed using gzip
		- A header table is also maintained on client and server side. So that repetitive headers are omitted from requests and responses
	- Server Push:
		- Server sends client resources that the server knows the client will ask for in subsequent requests
		- Server will send a special frame called PUSH_PROMISE
		- PUSH_PROMISE contains the stream id that will have the resource that the client will eventually request
	- Request Prioritization:
		- Certain requests can be prioritized. Otherwise the server processes requests asynchronously
		- When a PRIORITY frame is sent the server will allocate resources to complete this stream first
	- Security:
		- TLS is required

### Browsers
- Browsers show us a resource (HTML, PDF, etc.) on the basis of a URI (Uniform Resource Identifier)
- High-level infrastructure:
	- User interface
	- Browser engine 
		- marshals actions between the UI and rendering engine
	- Rendering engine 
		- displays requested content
	- Networking 
		- handles all http requests and other network interactions
	- UI backend
		- used for drawing widgets like combo boxes by exposing a generic interface
	- JS interpreter
		- executes JS and returns result to the rendering engine
	- Data storage
		- local storage etc.
- Main flow:
	- The rendering engine begins by requesting the initial content to be rendered from the networking layer
	- The content tree is made by parsing HTML and creating a tree with DOM nodes (e.g. `HTMLElementBody` for a `<body>` tag)
	- The render tree is made by parsing CSS data
	- Next, the layout is processed giving all nodes their coordinate positions on the screen
	- Then the render tree is traversed and each node is then painted using the UI backend layer, this is called painting
	- This flow can differ for different browsers and engines (webKit vs Gecko)

### DNS
- Naming system for Internet connected resources
- Readable names for IP addresses
- DNS maintains a list of domain names and their associated IP addresses
- Doesn't necessarily need to be a webpage, can be any resource like an image or video
