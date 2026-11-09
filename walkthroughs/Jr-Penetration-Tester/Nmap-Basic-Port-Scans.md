* `TCP Scan` - TCP is a connection-oriented protocol. It uses a three-way handshake to establish a connection.


* `UDP Scan` - UDP is a connectionless protocol. It does not use a handshake. Nmap may receive no response, making port states harder to determine.


* `TCP 3-Way Handshake` - TCP connection setup using three steps: SYN, SYN/ACK, and ACK.


* `SYN/ACK Flags` - SYN starts a TCP connection. SYN/ACK is the server's response, acknowledging the request and sending its own SYN.


* `TCP Connect Scan (-sT)` - Nmap uses the connect() system call to establish a full TCP connection using the three-way handshake.


* `TCP SYN Scan (-sS)` - Nmap sends a SYN packet and checks the response. If the port is open, it receives SYN/ACK and sends RST instead of completing the handshake. Also known as a Half-Open Scan.


* `UDP ICMP Responses` - ICMP Port Unreachable usually indicates a closed UDP port. No response may mean the port is open or filtered.
