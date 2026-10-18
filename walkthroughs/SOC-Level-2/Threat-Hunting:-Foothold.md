 * `Initial Access via Brute-Forcing SSH` - Gaining entry by guessing credentials repeatedly, spotted in logs when numerous failed login attempts are followed by a successful one.


* `Initial Access via Remote Code Execution (RCE)` - Exploiting software vulnerabilities to execute commands remotely without needing valid credentials beforehand.


* `Initial Access via Phishing Links and Attachments` - Deceiving users via links to harvest credentials or using malicious attachments to deliver payloads like malware and ransomware.


* `Execution via Command-Line Tools` - Using built-in native command-line tools like PowerShell, WMI, or bash to blend in with normal administrative activity and bypass detection.


* `Scheduled Task Creation` - Creating scheduled tasks or cron jobs to ensure persistence so the attacker regains access even if the current session is terminated.


* `Registry Key Modification` - Modifying Windows registry autostart keys like Run or RunOnce to ensure malicious commands or payloads execute automatically every time the system boots up.
