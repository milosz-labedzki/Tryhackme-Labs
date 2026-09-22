* `SSH Activity Logs` - Inspect all SSH daemon logs for connection attempts:
cat /var/log/auth.log | grep "sshd"

* `Successful SSH Authentication` - Filter logs for accepted SSH login events to detect legitimate or compromised access:
cat /var/log/auth.log | grep -E 'Accepted'

* `Nginx Access Log` - Location of Nginx web server access logs containing incoming HTTP/HTTPS requests:
/var/log/nginx/access.log

* `Auditd Executable Search (-x)` - Search audit logs for execution of a specific binary:
ausearch -i -x whoami

* `Process Tree Traversal (Auditd)` - Walk up parent process IDs using PID tracking to trace the root caller up to PID 1:
ausearch -i --pid <PID>

* `Supply Chain Compromise` - An attack vector where a trusted third-party vendor, software library, or dependency is compromised to breach downstream targets.

* `Process Tree Analysis` - Examining parent-child process relationships to determine the execution lineage and identify malicious execution sources.
