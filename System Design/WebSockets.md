WebSockets provide a persistent, full duplex connection between the client and server over a single TCP connection

## How do they work?

- WebSockets handshake using HTTP upgrade request
	- Step 1: Client requests an upgrade to WebSockets
	- Step 2: Server accepts and keeps the connection open
- Connection remains open for continuous data exchange
- Either client or server can send messages at any time
	- Step 3: Data is exchanged in real-time using frames
	- Step 4: Either party can close the connection when done
## Advantages

- Persistent connection
- Reduces overhead compared to HTTP polling
- Efficient for real-time apps