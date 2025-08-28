- Stands for HyperText Transfer Protocol
- The foundation of web communication
- Works over TCP/IP
## Key Features

- Text-based protocol
- Stateless
- Supports multiple methods
## How does it work?

- Client - Server Model
- Components of an HTTP Request:
	- Method: Define the action (GET, POST)
	- URL: The resource being requested
	- Headers: Metadata
	- Body: Data sent in POST/PUT
- Components of an HTTP Response:
	- Status Code: Indicates success or failure
	- Headers: Metadata about the response
	- Body (optional): The actual content

## The HTTP Request-Response Cycle

1. Step 1: The browser sends a request
2. Step 2: The web server processes the request
3. Step 3: The server generates a response and sends it back
4. Step 4: The browser renders the response
## Stateless Nature of HTTP

- HTTP does not retain memory of previous requests
- Each request is treated as an independent transactions
- Hard to maintain user sessions
- Each request must carry all necessary information
### How do we handle state?

- Cookies - Small pieces of data stored in the browser
- Sessions - Server-side storage of user state
- Tokens (JWT, OAuth) - Used for authentication & authorization
## HTTP Methods

- GET
- POST
- PUT
- DELETE
- PATCH
## HTTP Status Codes

- 1xx - Informational
- 2xx - Success
- 3xx - Redirection
- 4xx - Client Errors
- 5xx - Server Errors
## HTTPS

- It is the secure version of HTTP
- It uses SSL/TLS encryption
- Works on Port 443 instead of Port 80