## 1. **Client-Server Model**
- **Client:** A device or application that sends requests for resources or services (e.g., web browser).
- **Server:** A device or application that responds to client requests, providing resources or services (e.g., web server).

---

## 2. **IP Addressing**
- **IP Address:** A unique identifier for a device on a network.

### **IPv4:**
- 32-bit address space.
- Format: `xxx.xxx.xxx.xxx` (e.g., 192.168.0.1).
- Provides approximately 4.3 billion unique addresses.

### **IPv6:**
- 128-bit address space.
- Format: `xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx` (e.g., 2001:0db8:85a3:0000:0000:8a2e:0370:7334).
- Solves IPv4 address exhaustion, allowing a virtually unlimited number of addresses.

---

## 3. **IP Packets and Headers**
- **IP Packet:** A unit of data transmitted across the internet.
- **IP Header:** Contains metadata about the packet for routing and delivery.

### Key Fields in an IP Header:
1. **Source IP:** Address of the sender.
2. **Destination IP:** Address of the receiver.
3. **Version:** Indicates IPv4 or IPv6.
4. **Time to Live (TTL):** Limits the lifespan of the packet to prevent infinite looping.
5. **Protocol:** Indicates the transport protocol (e.g., TCP, UDP).

---

## 4. **TCP (Transmission Control Protocol)**
- A connection-oriented protocol that ensures reliable delivery of data between devices.
- Establishes a **three-way handshake** before data transmission.

### Key Fields in a TCP Header:
1. **Source Port:** Port number of the sender.
2. **Destination Port:** Port number of the receiver.
3. **Sequence Number:** Ensures ordered delivery of data.
4. **Acknowledgment Number:** Confirms receipt of data.
5. **Flags:** Control data flow (e.g., SYN, ACK, FIN).
6. **Checksum:** Validates data integrity.

---

## 5. **Private and Public IP Addresses**
- **Private IP:** Used within private networks (e.g., home or office). Examples:
  - 192.168.0.0 – 192.168.255.255
  - 10.0.0.0 – 10.255.255.255
- **Public IP:** Assigned to devices on the internet, globally unique.

---

## 6. **Static vs. Dynamic IP**
- **Static IP:** Fixed IP address assigned manually. Ideal for servers or network devices.
- **Dynamic IP:** Automatically assigned by **DHCP (Dynamic Host Configuration Protocol)**. Common for most users.

---

## 7. **Ports**
- Ports allow multiple services to run on the same IP address.
- Identified by a 16-bit number (range: 0–65535).

### Common Ports:
- **80:** HTTP (Web traffic).
- **443:** HTTPS (Secure web traffic).
- **22:** SSH (Secure Shell).
- **25:** SMTP (Email).
- **3306:** MySQL database.


