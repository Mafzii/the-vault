---
tags:
  - api
  - network
---
***Application Programming Interface***
	specifies how 2 software components communicate
### Rest APIs
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

### Common response codes
![[Response Codes Image.png]]

### JSON API
- https://rapidapi.com/blog/api-glossary/what-is-json-api-json-vs-graphql-vs-rest-api-comparison/#:~:text=JSON%20(JavaScript%20Object%20Notation)%20API,computers%20in%20different%20geographical%20areas.