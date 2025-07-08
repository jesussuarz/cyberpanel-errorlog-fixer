# Cyberpanel error_log Fixer

A simple bash script to automatically fix PHP error log permissions and logLevel configuration for all websites hosted on CyberPanel with OpenLiteSpeed.

**Author:** Jesus Suarez, SOPORTE SERVER

---

## What does this script do?

- Scans all vhosts on your CyberPanel server.
- Updates the `logLevel` to `WARNING` in each vhost's `vhost.conf`.
- Fixes ownership and permissions for each domain’s error log file.
- Restarts the OpenLiteSpeed service to apply changes.
- Works safely and non-destructively, only updating what’s needed.

---

## Quick Install & Run

Run this command as root to download and execute the script in one line:

```bash
curl -sSL https://raw.githubusercontent.com/jesussuarz/cyberpanel-errorlog-fixer/refs/heads/main/cyberpanel-errorlog-fix.sh | bash
```

## How it works
* Iterates through /usr/local/lsws/conf/vhosts/*/vhost.conf
* Updates logLevel in each vhost’s config to WARNING
* Ensures error log files in /home/DOMAIN/logs/ are owned by nobody:nobody and set to permissions 644
* Restarts the OpenLiteSpeed service (lscpd)

Requirements
* Must be run as root
* CyberPanel with OpenLiteSpeed (default paths)
* Bash shell and standard Unix utilities

Contributions and suggestions are welcome. Use responsibly!
