<p align="center">
  <img src="../006/assets/TCP_3.png">
</p>

# Table of contents

- [TCP and UDP](#tcp-and-udp)
  - [TCP](#tcp)
  - [UDP](#udp)
  - [Common Ports](#common-ports)
  
# TCP and UDP

TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are two fundamental transport layer protocols used in computer networking. They play crucial roles in data transmission by providing different approaches to data exchange between network applications.

## TCP

TCP is a connection-oriented protocol, meaning it establishes a connection between the sending and receiving applications before data transfer begins. This connection ensures reliable and ordered data transmission, guaranteeing that all data packets reach their destination in the correct sequence without corruption or loss. TCP employs a three-way handshake process to establish a connection before data transmission and uses acknowledgment (ACK) and negative acknowledgment (NAK) mechanisms to ensure data integrity.

### TCP Handshake

The TCP handshake, also known as the three-way handshake, is a process used to establish a connection between two devices over a TCP/IP network. It is a crucial step in ensuring reliable and secure data transmission between applications. The handshake involves the exchange of three segments between the client and the server.

*Step 1: SYN (Synchronize)*

The client initiates the connection by sending a SYN segment to the server. The SYN segment contains a sequence number, which is a unique identifier used to track the order of data packets. The client also sets the SYN flag to 1, indicating that it is requesting a connection.

*Step 2: SYN-ACK (Synchronize-Acknowledgment)*

Upon receiving the SYN segment, the server sends back a SYN-ACK segment to the client. The SYN-ACK segment contains the server's own sequence number and acknowledges the client's sequence number with an ACK flag set to 1. This acknowledgment indicates that the server has received the client's SYN segment and is willing to establish a connection.

*Step 3: ACK (Acknowledgment)*

Finally, the client sends an ACK segment to the server, acknowledging the server's SYN-ACK segment. This ACK flag set to 1 completes the handshake, and the connection is established. Both devices can now begin exchanging data reliably.

## UDP

UDP, in contrast to TCP, is a connectionless protocol. It does not establish a connection before data transfer and sends data packets independently without guarantees of delivery or order. UDP is considered unreliable as it does not employ error detection or correction mechanisms, making it suitable for applications that prioritize speed over reliability, such as real-time multimedia streaming or gaming.

## Common Ports

| Protocol | Port   | Service |
| ---------| -------| --------|
| TCP      | 20, 21 | File Transfer (FTP)|
| TCP      | 22     | Secure Shell (SSH) |
| UDP      | 67, 68 | Dynamic Host Configuration (DHCP)|