* `Working With Logs` - Linux stores system activity in human-readable plain text files in `/var/log`, allowing log analysis using standard CLI text processing tools.

* `Login and Logout Events` - User authentication activity recorded in `/var/log/auth.log`, filtered via: `cat /var/log/auth.log | grep -E 'session opened|session closed'`

* `User Management Events` - User creation, password changes, and account deletions logged in `/var/log/auth.log`, filtered via: `cat /var/log/auth.log | grep -E '(passwd|useradd|usermod|userdel)\['`

* `System and Kernel Logs` - Core operational logs where `/var/log/syslog` records general system activity and `/var/log/kern.log` tracks low-level kernel messages.

* `Package Manager Logs` - Log files tracking software installation and updates, located at `/var/log/dpkg.log` (Debian/Ubuntu) or `/var/log/dnf.log` (RHEL/CentOS).

* `Bash History` - Per-user history recording executed shell commands upon session logout, inspected via `cat ~/.bash_history` or using the live `history` command.

* `execve` - The primary Linux system call used to execute programs and binaries, monitored to track all command execution on the system.

* `Auditd & ausearch` - The Linux Audit framework logging kernel-level events to `/var/log/audit/audit.log`, searched and formatted using: `ausearch -i -k <key>`

* `Auditd File Monitoring` - Configuring auditd rules to detect unauthorized access or changes to critical files (such as `/etc/ssh/sshd_config`).
