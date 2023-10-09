# Nmap
```
# Nmap 7.94 scan initiated Tue Sep 19 12:18:15 2023 as: nmap -sC -sV -oN nmap.txt 10.10.181.166
Nmap scan report for 10.10.181.166
Host is up (0.30s latency).
Not shown: 998 closed tcp ports (conn-refused)
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 7.2p2 Ubuntu 4ubuntu2.6 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey:
|_  256 aa:34:22:49:39:52:2e:48:dc:07:25:ea:78:7b:04:91 (ED25519)
80/tcp open  http    Apache/2.4.18 (Ubuntu)
|_http-server-header: Apache/2.4.18 (Ubuntu)
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
# Nmap done at Tue Sep 19 12:24:50 2023 -- 1 IP address (1 host up) scanned in 394.97 seconds
```