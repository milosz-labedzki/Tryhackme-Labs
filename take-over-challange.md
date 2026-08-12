# Subdomain & Virtual Host Enumeration Walkthrough

## Tools Used

* `ffuf` - Fast web fuzzer used for discovering virtual hosts (vhosts) and hidden subdomains by injecting wordlists into HTTP `Host` headers.
* `curl` - Command-line HTTP client used to manually inspect server responses, test specific `Host` headers, and bypass self-signed SSL warnings (`-k`).
* `openssl` - Toolkit used to inspect remote TLS certificates (`s_client`) and extract `Subject Alternative Names` (SANs) from target servers.
* `/etc/hosts` - Local operating system routing file used to map custom `.thm` domain names and subdomains directly to the target IP address.
* `SecLists` - Pre-installed collection of security wordlists used by `ffuf` for subdomain brute-forcing (`subdomains-top1million-110000.txt`).

---

## Step-by-Step Methodology

* `Step 1` - Map the target IP address and primary domain name in the local hosts file.
* `Step 2` - Perform virtual host fuzzing using wordlists to discover valid subdomains.
* `Step 3` - Append the newly discovered subdomain to the local hosts file.
* `Step 4` - Inspect the TLS certificate's Subject Alternative Name field to uncover hidden infrastructure.
* `Step 5` - Query the hidden subdomain directly via curl or a browser to retrieve the flag.
EOF
