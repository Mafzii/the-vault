---
tags:
  - api
  - network
  - backend
---
***Application Programming Interface***
	specifies how 2 software components communicate
### REST
- REST defines a set of functions GET, POST, PUT, DELETE to carry out operations on server data
- APIs that are REST compliant are called RESTful APIs
- Clients and servers communicate through HTTP
	- Implementation of both are done separately, so the client or server side code can be changed without affecting the operation of the other
- REST APIs are stateless
	- Servers do not save client data between requests
	- This means each request is processed independently of previous requests
- Client requests have the following:
	- An HTTP verb (GET, POST, PUT, DELETE)
	- A path to access resources (URI)
		- convention for path is the plural form of the resource
		- e.g. for a user, getting a list of all users will be /users
	- Header to provide supplementary information
		- e.g. Accept: application/json
	- Message body with payload (optional)
- REST Principles
	- Client-server architecture. The sender and receiver are independent of each other regarding technology, platforming, programming language, and so on.
	- Layered. The server can have several intermediaries that work together to complete client requests, but they are invisible to the client.
	- Uniform interface. The API returns data in a standard format that is complete and fully useable.
	- Stateless. The API completes every new request independently of previous requests.
	- Cacheable. All API responses are cacheable.
	- Code on demand. The API response can include a code snippet if required.
### Common response codes
![[Response Codes Image.png]]

### JSON API
- https://rapidapi.com/blog/api-glossary/what-is-json-api-json-vs-graphql-vs-rest-api-comparison/#:~:text=JSON%20(JavaScript%20Object%20Notation)%20API,computers%20in%20different%20geographical%20areas.
- Automatic caching, in REST you would have to implement caching strategies yourself
- Built in error msg field with standard messages
- Can request partial responses if only a certain field is needed

### SOAP
- Uses XML only to communicate via HTTP
- Better suited for security out of the box, in REST other modules would be needed to make it secure
- Generally used to extend legacy systems already built with SOAP APIs
- ACID compliance is built in out of the box

### gRPC
- Remote Procedure Call framework
- RPC is a protocol that allows a program to execute a procedure of another program located on another computer. The great advantage is that the developer doesn’t need to code the details of the remote interaction. The remote procedure is called like any other function. But the client and the server can be coded in different languages.