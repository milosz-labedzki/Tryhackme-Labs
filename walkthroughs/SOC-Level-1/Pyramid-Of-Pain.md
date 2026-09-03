* `Pyramid Of Pain` - A conceptual model developed by David J. Bianco that ranks threat indicators based on the level of difficulty and operational pain an adversary experiences when defenders detect and block them.

* `Hash values` - The bottom (Trivial) tier of the pyramid, consisting of fixed-length digital fingerprints (e.g., MD5, SHA-256) used to uniquely identify malicious files, which attackers can easily alter by modifying a single byte.

* `virus total` - An online threat intelligence platform and scanner used by security analysts to inspect suspicious files, hashes, domains, and IP addresses to identify malware.

* `IP Address` - The second (Easy) tier of the pyramid, representing numerical network identifiers used for command and control or payload hosting, which attackers can change quickly using proxies or Fast Flux techniques.

* `Domain Names` - The third (Simple) tier of the pyramid, representing web addresses registered or compromised by attackers to host attack infrastructure, requiring domain registration or DNS changes to replace.

* `Host Artifacts` - The fourth (Annoying) tier of the pyramid, comprising residual system modifications left by malicious activity on a target host, such as registry keys, dropped files, or process executions.

* `Network Artifacts` - The fifth (Annoying) tier of the pyramid, referring to distinctive patterns embedded in network traffic, such as custom User-Agent strings, specific URI patterns, or HTTP header signatures.

* `Tools` - The sixth (Challenging) tier of the pyramid, consisting of software utilities, backdoor frameworks, and scripts (e.g., Mimikatz, maldocs) used by attackers, forcing them to re-engineer tools if blocked.

* `TTPs` - Tactics, Techniques & Procedures; the apex (Tough) tier representing the adversary's overarching attack behaviors, strategies, and operational plans, which are the most difficult and costly for an attacker to change.
