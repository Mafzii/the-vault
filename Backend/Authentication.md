---
tags:
  - backend
---
### JWT
- JSON web tokens (JWT) is an open standard for secure communication between client and server.
- A JWT string is a serialization of base64 characters and is made up of 3 parts separated by dots. The JWT looks something like this: xxxxx.yyyyy.zzzzz.
- The token contains a set of claims. These claims will contain information such as who issued the token, how long it is valid for, etc.
- Once decoded the token will produce the following:
	1. The header
	2. The payload
	3. The signature
- The header contains the type of token (JWT) and the signing algorithm
- The payload contains the claims no claim is mandatory by default. Some standards like OAuth 2.0 require certain claims to be sent in the token.
- The signature ensures the token has not been altered. This can be done with a secret (key) only known to the sender and receiver or the sender encodes it with his private key and the receiver decodes it with the senders public key.
- Example: OAuth Bearer Tokens
	- An authorization server creates a JWT at the request of a client and signs it so that it cannot be altered by any other party. The client will then send this JWT with its request to a REST API. The REST API will verify that the JWT’s signature matches its payload and header to determine that the JWT is valid. When the REST API has verified the JWT, it can use the claims to either grant or deny the client’s request.

- Check out refresh and access token authentication for user session authentication (use in projects)