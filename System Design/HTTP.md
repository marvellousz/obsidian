## 1. HTTP (Hypertext Transfer Protocol)
- **Definition**: A protocol for transferring data (HTML, JSON, etc.) over the web.
- **Usage**: Powers communication between clients (browsers) and servers.
- **Versions**: HTTP/1.1, HTTP/2, and HTTP/3.

---

## 2. Client-Server Model
- **Client**: The requester (e.g., a web browser or app) that sends HTTP requests to the server.
- **Server**: Responds to client requests by providing data or performing actions (e.g., returning a webpage or updating a database).

---

## 3. RPC (Remote Procedure Call)
- **Definition**: A protocol where a client executes functions on a remote server as if they were local.
- **Common Examples**: gRPC, XML-RPC, JSON-RPC.
- **Difference from HTTP**: Focuses on method execution rather than resource transfer.

---

## 4. Endpoints
- **Definition**: URLs exposed by a server for interaction, such as `/api/users` or `/login`.
- **Example**: `https://example.com/api/users` is an endpoint for managing user data.

---

## 5. HTTP Methods
Used to perform specific actions on endpoints:
- **GET**: Retrieve data (read).
- **POST**: Submit data (create).
- **PUT**: Update/replace existing data.
- **DELETE**: Remove data.

---

## 6. CRUD Operations
- **Create**: Add new records (e.g., `POST`).
- **Read**: Fetch existing records (e.g., `GET`).
- **Update**: Modify records (e.g., `PUT` or `PATCH`).
- **Delete**: Remove records (e.g., `DELETE`).

---

## 7. HTTP Status Codes
Used by servers to indicate the outcome of a request:
- **1xx**: Informational
  - 101 Switching Protocols
- **2xx**: Success
  - 200 OK
  - 201 Created
- **3xx**: Redirection
  - 301 Moved Permanently
  - 302 Found
- **4xx**: Client Errors
  - 400 Bad Request
  - 404 Not Found
- **5xx**: Server Errors
  - 500 Internal Server Error
  - 503 Service Unavailable

---

## 8. SSL (Secure Sockets Layer) & TLS (Transport Layer Security)
- **SSL**: The predecessor of TLS, used to encrypt communications between clients and servers.
- **TLS**: A modern, more secure version of SSL.
- **Purpose**: Encrypt data to ensure privacy and security during transmission.
- **Common Use**: HTTPS (HTTP Secure) relies on TLS.
