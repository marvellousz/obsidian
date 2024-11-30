Switching in networking refers to the method used to forward data from one device to another across a network. It determines the path that data follows from the sender to the receiver. Switching is a critical concept for efficient network communication, especially in large-scale networks like the internet.

---

## Components of a Switched Network

1. **Switching Nodes**:
   - Intermediate devices (e.g., routers, switches) that route data through the network.
   - Do not process or modify the data but determine its optimal path.
2. **Links**:
   - Connections (wired or wireless) between nodes.
3. **End Nodes**:
   - Devices like computers, phones, or servers that send or receive data.

---

## Types of Switching

### 1. **Circuit Switching**
- **Definition**: A dedicated communication path is established between two devices for the duration of a session.
- **Characteristics**:
  - Connection-oriented.
  - Provides a constant bandwidth and quality of service (QoS).
  - Requires a setup phase before communication starts.
- **Example**: Traditional telephone networks.
- **Steps**:
  1. Establish a circuit between sender and receiver.
  2. Transmit data over the dedicated path.
  3. Terminate the circuit when the session ends.
- **Advantages**:
  - Guaranteed delivery and real-time communication.
  - Suitable for voice and video calls.
- **Disadvantages**:
  - Inefficient resource usage when the line is idle.
  - Limited scalability.

---

### 2. **Packet Switching**
- **Definition**: Data is divided into small units called packets, which are transmitted independently over the network.
- **Characteristics**:
  - Connectionless or connection-oriented.
  - No dedicated path; packets may take different routes to the destination.
  - More efficient use of network resources.
- **Types of Packet Switching**:
  - **Datagram Switching**:
    - Connectionless model.
    - Each packet contains the destination address and is routed independently.
    - Packets may arrive out of order or be lost.
    - Example: IP-based communication.
  - **Virtual-Circuit Switching**:
    - Connection-oriented model.
    - A logical path is established before data transfer, and all packets follow this path.
    - Ensures ordered delivery of packets.
    - Example: MPLS (Multiprotocol Label Switching), ATM (Asynchronous Transfer Mode).

---

### 3. **Message Switching**
- **Definition**: Entire messages are transmitted from the sender to the receiver via intermediate nodes, where each node stores the message temporarily before forwarding it.
- **Characteristics**:
  - Connectionless.
  - No need for a dedicated path.
  - Store-and-forward mechanism.
- **Steps**:
  1. Sender transmits the entire message to the first node.
  2. The node stores the message temporarily and forwards it to the next node.
  3. The process repeats until the message reaches the destination.
- **Advantages**:
  - Efficient for low-bandwidth networks.
  - Can handle large messages.
- **Disadvantages**:
  - High latency due to storage delays.
  - Requires significant memory at intermediate nodes.
- **Example**: Early telegraph systems, some email systems.

---

## Taxonomy of Switching Techniques

| Switching Type        | Connection Type       | Characteristics                                      | Examples                        |
|-----------------------|-----------------------|----------------------------------------------------|---------------------------------|
| **Circuit Switching** | Connection-oriented   | Dedicated path, real-time, fixed bandwidth         | Telephone networks             |
| **Datagram Switching**| Connectionless       | Independent packets, variable route, unordered     | Internet (IP protocol)         |
| **Virtual-Circuit**   | Connection-oriented   | Logical path, ordered delivery, guaranteed QoS     | MPLS, ATM                      |
| **Message Switching** | Connectionless       | Store-and-forward, high latency, large messages    | Early email, telegraph systems |

---

## Simple Switched Network

A simple switched network consists of:
1. **Nodes**:
   - Devices like switches or routers that manage data forwarding.
2. **Links**:
   - Physical or logical connections between nodes.
3. **End Devices**:
   - Devices like PCs or smartphones that initiate or receive communication.

Data in a switched network moves from source to destination by:
- Passing through one or more nodes.
- Using a switching technique to determine the path.

---

## Comparing Switching Techniques

| Feature                | Circuit Switching     | Datagram Switching      | Virtual-Circuit Switching  | Message Switching      |
|------------------------|-----------------------|--------------------------|----------------------------|------------------------|
| **Path**               | Dedicated path       | No dedicated path        | Logical path established   | No dedicated path      |
| **Delivery**           | Continuous           | Unordered, may be lost   | Ordered and reliable       | Entire message         |
| **Setup Phase**        | Required             | Not required             | Required                   | Not required           |
| **Resource Usage**     | Inefficient          | Efficient                | Efficient                  | Moderate               |
| **Latency**            | Low                  | Low to moderate          | Low to moderate            | High                   |
| **Applications**       | Voice calls          | Internet traffic         | Real-time streaming        | Bulk email transfer    |

---

## Real-World Applications

- **Circuit Switching**:
  - Voice over PSTN (Public Switched Telephone Network).
- **Datagram Packet Switching**:
  - Browsing websites (HTTP over IP).
  - File downloads (FTP).
- **Virtual-Circuit Packet Switching**:
  - Video conferencing (MPLS).
  - ATM-based banking networks.
- **Message Switching**:
  - Email systems.
  - Early telegraph networks.

---

