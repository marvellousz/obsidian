## 1. FTP (File Transfer Protocol)
- **Definition**: A protocol used to transfer files between a client and a server over a network.
- **Purpose**: Upload, download, or manage files on a remote server.
- **Modes**:
  - Active Mode: Server opens a connection to the client for data transfer.
  - Passive Mode: Client opens the connection for data transfer.
- **Ports**:
  - Default Command Port: 21
  - Data Transfer Port: 20 (active mode)
- **Security**: 
  - **FTPS**: Secure FTP using SSL/TLS.
  - **SFTP**: Secure File Transfer Protocol, which uses SSH for encryption.

---

## 2. SMTP (Simple Mail Transfer Protocol)
- **Definition**: A protocol used to send emails from a client to a server or between mail servers.
- **Purpose**: Handles outgoing email communication.
- **Ports**:
  - Port 25: Default (may be blocked for spam prevention).
  - Port 587: For secure, authenticated email submissions.
  - Port 465: Deprecated but sometimes used for SMTP over SSL.
- **Usage**: Works with IMAP/POP for receiving emails.

---

## 3. SSH (Secure Shell)
- **Definition**: A protocol that allows secure, encrypted communication between two computers.
- **Purpose**:
  - Remote login to servers.
  - Secure file transfers (e.g., via **SFTP**).
  - Running commands on remote systems.
- **Features**:
  - **Encryption**: Protects data from interception.
  - **Key Authentication**: Uses public/private key pairs for secure authentication.
  - **Port Forwarding**: Tunnels network traffic securely.
- **Default Port**: 22.

---

## 4. WebRTC (Web Real-Time Communication)
- **Definition**: A technology enabling real-time communication (audio, video, and data) directly between browsers or apps without requiring an intermediary server.
- **Purpose**:
  - Video and voice calls (e.g., video conferencing apps).
  - Peer-to-peer file sharing.
- **Key Features**:
  - **Media Streams**: Enables transmission of audio and video.
  - **Data Channels**: Transfers arbitrary data (e.g., text, files).
  - **NAT Traversal**: Uses STUN and TURN servers for establishing connections through firewalls.
- **Protocols Used**:
  - **DTLS**: Encrypts data channels.
  - **SRTP**: Encrypts audio and video streams.
- **Applications**: Zoom, Google Meet, online gaming, etc.
