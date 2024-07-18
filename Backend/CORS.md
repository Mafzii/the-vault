---
tags:
  - backend
  - network
---
If we send a fetch request to another web-site, it will probably fail.

For instance, let’s try fetching http://example.com:
```
try {
  await fetch('http://example.com');
} catch(err) {
  alert(err); // Failed to fetch
}
```
Fetch fails, as expected.

The core concept here is origin – a domain/port/protocol triplet.

Cross-origin requests – those sent to another domain (even a subdomain) or protocol or port – require special headers from the remote side.

That policy is called “CORS”: Cross-Origin Resource Sharing.

This is done to prevent scripts from one site running on another site, preventing cyber attacks

### Safe Requests

Whenever a cross-origin request is made the browser adds the `Origin` header to the request.
If the server accepts then the `Access-Control-Allow-Origin` header is added to the response with the `Origin` or a `*`.

A request is safe if it satisfies two conditions:
- Safe method: GET, POST or HEAD
- Safe headers – the only allowed custom headers are:
	- Accept,
	- Accept-Language,
	- Content-Language,
	- Content-Type with the value `application/x-www-form-urlencoded`, `multipart/form-data` or `text/plain`.
