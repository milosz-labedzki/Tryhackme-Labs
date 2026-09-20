* `T1133 (External Remote Services)` - MITRE ATT&CK technique where attackers target exposed remote access protocols (like RDP, SSH, or VNC) using weak or stolen credentials.

* `T1190 (Exploit Public-Facing Application)` - MITRE ATT&CK technique where threat actors exploit software vulnerabilities or misconfigurations in Internet-exposed web applications and servers.

* `Detecting RDP Brute Force` - Searching Windows Security Logs for a high volume of Event ID 4625 (Failed Logon) associated with Logon Type 3 (Network) or 10 (RemoteInteractive) from external IPs.

* `Detecting RDP Initial Access` - Filtering Security Logs for Event ID 4624 (Successful Logon) following failed logon attempts to identify the specific compromised account.

* `Tracking RDP Post-Exploitation` - Extracting the "Logon ID" from a successful Logon Type 10 (ID 4624) event and searching Sysmon logs with that Logon ID to view all processes executed by the attacker.

* `Sysmon Event ID 1` - Process Creation event that tracks command execution, parent processes, user accounts, and unique Logon IDs.

* `Sysmon Event ID 11` - File Create event that logs when a file is created or overwritten, helping detect dropped malware, payloads, or staged files.

* `Current State of Phishing` - A primary social engineering vector that targets end-users directly to bypass perimeter firewalls and deliver malicious payloads via email.

* `LNK Attachments` - Malicious Windows shortcut files (.lnk) disguised as benign documents or links that execute hidden background scripts (e.g., PowerShell, VBS, BAT) when opened.
