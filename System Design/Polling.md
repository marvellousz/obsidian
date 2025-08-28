*Long Polling* is a technique where the client sends a request to the server and waits until the server has new data to respond with
- It differs from regular polling because the server holds the request until the new data is available
## How does it work?

- Client makes an HTTP request
- Server holds the request until data is available
- Server responds with new data
- Client immediately sends another request
## Differences between WebSockets and Long Polling

- Use case is that of a periodic updates like notification system. Like twitter uses long polling for notification and in IOT devices uses this for intermittent updates.