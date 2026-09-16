* `Event Viewer` - A built-in Windows administrative tool used to view, search, and analyze system, security, and application logs.

* `Event ID` - A unique numerical code assigned by Windows to identify specific types of system occurrences and security events.

* `4624 (Successful Logon)` - Windows Security Log event triggered when an account successfully logs on to the host.

* `4625 (Failed Logon)` - Windows Security Log event triggered when a logon attempt fails, vital for detecting brute-force attacks.

* `4720 / 4722 / 4738 (Account Management)` - Events logged when a user account is created, enabled, or modified; monitored to detect backdoor creation or unauthorized account activation.

* `4725 / 4726 (Account Disablement / Deletion)` - Events logged when a user account is disabled or deleted, which attackers may use to disrupt SOC defense or wipe access trails.

* `4723 / 4724 (Password Change / Reset)` - Events logged when a user changes or an admin resets an account password, indicating potential privilege abuse or unauthorized takeover.

* `4732 / 4733 (Group Membership Changes)` - Events logged when a user is added to or removed from a security group, crucial for spotting privilege escalation (e.g., adding accounts to Administrators).

* `Sysmon vs Security Log` - Sysmon provides detailed, granular activity monitoring (process trees, network connections) whereas standard Windows Security Logs focus primarily on authentication and native audit events.

* `Sysmon Event ID 1` - Process Creation event in Sysmon that captures executed process binaries, parent processes, user context, and full command-line arguments.

* `Sysmon Event IDs 11 / 13 (vs Security Log 4656 / 4657)` - Sysmon events tracking File Creation (11) and Registry Modifications (13) to catch malware persistence; alternatives in Security Logs are 4656 and 4657 (disabled by default).

* `Sysmon Event IDs 3 / 22` - Sysmon events tracking Network Connections (3) and DNS Queries (22) to detect malicious outbound traffic and C2 communications, which have no direct native Security Log equivalents.

* `PowerShell History File` - A text file recording executed PowerShell commands for audit and forensic analysis, accessible via: `type C:\Users\<USER>\AppData\Roaming\Microsoft\Windows\PowerShell\PSReadline\ConsoleHost_history.txt`
