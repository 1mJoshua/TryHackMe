# nmap
```bash
# Nmap 7.93 scan initiated Sat Sep 23 03:10:40 2023 as: nmap -sC -sV -oN nmap.txt 10.10.162.72
Nmap scan report for 10.10.162.72
Host is up (0.31s latency).
Not shown: 997 filtered tcp ports (no-response)
PORT    STATE  SERVICE  VERSION
22/tcp  closed ssh
80/tcp  open   http     Apache httpd
|_http-title: Site doesn't have a title (text/html).
|_http-server-header: Apache
443/tcp open   ssl/http Apache httpd
| ssl-cert: Subject: commonName=www.example.com
| Not valid before: 2015-09-16T10:45:03
|_Not valid after:  2025-09-13T10:45:03
|_http-title: Site doesn't have a title (text/html).
|_http-server-header: Apache

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
# Nmap done at Sat Sep 23 03:11:28 2023 -- 1 IP address (1 host up) scanned in 48.29 seconds
```