---
tags:
  - project
---

![[Spring JWT Setup.png]]

### Overview
- Running on a Spring Boot Container on a Apache Tomcat embedded server
- Whenever a request is made the JWT Auth Filter is executed:
	- Checks if there is a JWT token
		- Send 403 if it does not exist
	- Checks the JWT token and extracts the information(user details) to fetch the users information from the database through the service
	- On response we make some checks like if the user exists or not
	- Next we validate the JWT token
		- JWT service takes the user and token as parameters
		- Check if the token is for that user or if its expired
		- If it is a valid token
			- Update the security context holder and set the value to the authenticated user
			- Dispatch the request and send to the controller 
			- Logic for the service
			- Successful response sent to the user

