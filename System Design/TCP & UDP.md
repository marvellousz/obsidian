## 1. **TCP (Transmission Control Protocol):**
- **Type:** Connection-oriented protocol.
- **Reliability:** Ensures data is delivered accurately and in order.
- **Features:**
  - Error checking and retransmission.
  - Flow control to avoid overwhelming the receiver.
  - Provides ordered delivery of packets.

### **Three-Way Handshake in TCP:**
The handshake establishes a reliable connection between the client and the server:
1. **SYN (Synchronize):** 
   - Client sends a SYN packet to the server to request a connection.
2. **SYN-ACK (Synchronize-Acknowledge):** 
   - Server responds with a SYN-ACK packet, indicating readiness to establish the connection.
3. **ACK (Acknowledge):** 
   - Client sends an ACK packet to acknowledge the server's response, completing the handshake.

Once the handshake is completed, data transmission begins.

---

## 2. **UDP (User Datagram Protocol):**
- **Type:** Connectionless protocol.
- **Reliability:** Unreliable (no error checking or retransmission).
- **Features:**
  - Faster than TCP because it has no connection setup or acknowledgment.
  - Ideal for real-time applications like video streaming, VoIP, and gaming.

---

## 3. **Comparison: TCP vs. UDP**
| Feature                 | TCP                                   | UDP                                |
|-------------------------|---------------------------------------|------------------------------------|
| **Connection Type**     | Connection-oriented (3-way handshake) | Connectionless                     |
| **Reliability**         | Reliable (error-checking, retransmission) | Unreliable                        |
| **Speed**               | Slower due to overhead                | Faster due to minimal overhead     |
| **Use Cases**           | File transfer, web browsing           | Streaming, gaming, DNS queries     |

---

## 4. **Internet Protocol Suite:**
The Internet Protocol Suite (TCP/IP model) is the foundation of internet communication. Key layers:
1. **Application Layer:**
   - Protocols: HTTP, FTP, DNS, SMTP.
   - Provides user interfaces and facilitates communication between applications.

2. **Transport Layer:**
   - Protocols: TCP, UDP.
   - Ensures reliable (TCP) or fast (UDP) delivery of data.

3. **Internet Layer:**
   - Protocols: IP (IPv4, IPv6).
   - Handles packet routing and addressing.

4. **Network Access Layer:**
   - Deals with hardware-level protocols for data transmission (e.g., Ethernet, Wi-Fi).

---

## 5. **TCP Key Features and Terms:**
- **Reliable:** Ensures data is delivered without loss, duplication, or corruption.
- **SYN (Synchronize):** Used to initiate a connection.
- **ACK (Acknowledge):** Confirms receipt of data or connection requests.
- **Flow Control:** Adjusts data transmission speed to match receiver capacity.
- **Error Checking:** Verifies data integrity using checksums.
