## Components

1. Client
2. Server
3. Network

## Request - Response Cycle

1. Browser requests a website
2. DNS resolves domain to IP address
3. Browser sends an HTTP GET request to the web server
4. Web server processes request, fetches HTML, queries the database if needed
5. Server sends an HTTP response with a status code (200 OK) and the webpage content 
6. Browser renders the webpage

## Synchronous and Asynchronous Communication

**Synchronous**: Client waits for a response before proceeding. Eg: REST Apis

**Async**: Client dosen't wait for a response and can perform other tasks. Eg: WebSockets

## Stateful and Stateless

**Stateless**: No memory of past interactions; each request is independent

**Stateful**: Maintain session information across requests