* `Subnetworks` - Different networks can communicate through a router. No ping response does not always mean the host is offline.


* `TCP` - A transport protocol. SYN/ACK or RST responses can indicate that a host is reachable.


* `UDP` - A transport protocol. An ICMP Port Unreachable response can indicate that the host is reachable, but the UDP port is closed.


* `ICMP` - A network protocol used for error messages and host discovery. Different ICMP message types can be used to check if a host is reachable.


* `ARP` - Address Resolution Protocol. It finds the MAC address linked to a known IP address on a local network.


* `ARP Scan` - Uses ARP requests to discover active hosts on the local network. An ARP reply provides the host's MAC address.


* `ICMP Echo Scan` - Uses ICMP Echo Request (Type 8) and waits for Echo Reply (Type 0).


* `ICMP Timestamp Scan` - Uses ICMP Timestamp Request (Type 13) and waits for Timestamp Reply (Type 14).


* `ICMP Address Mask Scan` - Uses ICMP Address Mask Request (Type 17) and waits for Address Mask Reply (Type 18).


* `TCP SYN Ping Scan` - Sends TCP SYN packets and looks for SYN/ACK or RST responses to discover active hosts.


* `TCP ACK Ping Scan` - Sends TCP ACK packets and looks for RST responses to identify reachable hosts.


* `UDP Ping Scan` - Sends UDP packets, often to closed ports. An ICMP Port Unreachable response can confirm that a host is reachable.


* `-n` - Disables DNS lookups during scanning.


* `-R` - Forces reverse DNS lookups for all hosts.


* `-sn` - Performs host discovery only without scanning ports.
