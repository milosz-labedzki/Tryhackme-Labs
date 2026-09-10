* `Host-Centric Logs` - Event records generated directly by individual devices (endpoints, servers) tracking local activities like user logins, process creation, and file changes.

* `Network-Centric Logs` - Log data collected from network devices (firewalls, routers, switches) capturing communication details like source/destination IPs, ports, and protocols.

* `Firewalls` - Security devices or software that monitor and filter incoming and outgoing network traffic based on predefined security rules.

* `Intrusion Detection/Prevention Systems (IDS/IPS)` - Security tools that monitor network traffic for malicious activity; IDS alerts on threats, while IPS actively blocks them.

* `Routers and Switches` - Core networking hardware; routers direct data packets between different networks, while switches connect devices within the same local network.

* `Web Proxies` - Intermediary servers that sit between web clients and destination servers to inspect, filter, cache, and control web traffic.

* `VPN` - Virtual Private Network; an encrypted connection established over a public network to allow secure, private access to internal network resources.

* `The Perimeter` - The outer boundary that separates an organization's private, trusted internal network from untrusted external networks like the Internet.

* `Importance of Network Perimeter` - Protecting the network border serves as the primary barrier to prevent unauthorized external access and stop initial attack vectors.

* `Monitoring the perimeter` - The process of inspecting logs and traffic at network entry points (firewalls, proxies, border routers) to spot potential intrusion attempts.

* `head firewall.log` - A Linux command that outputs the first 10 lines of the `firewall.log` file to quickly inspect its structure.

* `cat firewall.log | grep "BLOCK" | head` - A Linux command pipeline that searches `firewall.log` for lines containing "BLOCK" and displays only the first 10 matching entries.

* `cat firewall.log | grep "BLOCK" | cut -d' ' -f5 | cut -d: -f1 | sort -nr | uniq -c` - A Linux command pipeline that filters blocked entries, extracts IP addresses, counts unique occurrences, and sorts them to highlight top blocked sources.

* `cat firewall.log | grep [REDACTED] | grep "ALLOW"` - A Linux command pipeline that searches `firewall.log` for a specific target value and displays only its allowed traffic events.
