# Nmap
```
# Nmap 7.94 scan initiated Tue Sep 19 14:39:40 2023 as: nmap -Pn -sC -sV -oN nmap.txt 10.10.247.80
Nmap scan report for 10.10.247.80
Host is up (0.28s latency).
Not shown: 976 closed tcp ports (conn-refused)
PORT      STATE    SERVICE              VERSION
22/tcp    open     ssh                  OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey:
|   2048 4a:b9:16:08:84:c2:54:48:ba:5c:fd:3f:22:5f:22:14 (RSA)
|   256 a9:a6:86:e8:ec:96:c3:f0:03:cd:16:d5:49:73:d0:82 (ECDSA)
|_  256 22:f6:b5:a6:54:d9:78:7c:26:03:5a:95:f3:f9:df:cd (ED25519)
80/tcp    open     http                 Apache httpd 2.4.29 ((Ubuntu))
| http-cookie-flags:
|   /:
|     PHPSESSID:
|_      httponly flag not set
|_http-title: HackIT - Home
|_http-server-header: Apache/2.4.29 (Ubuntu)
524/tcp   filtered ncp
722/tcp   filtered unknown
1050/tcp  filtered java-or-OTGfileshare
1052/tcp  filtered ddt
1110/tcp  filtered nfsd-status
1322/tcp  filtered novation
1443/tcp  filtered ies-lm
1666/tcp  filtered netview-aix-6
1700/tcp  filtered mps-raft
1935/tcp  filtered rtmp
3168/tcp  filtered poweronnud
4446/tcp  filtered n1-fwp
4899/tcp  filtered radmin
5102/tcp  filtered admeng
5877/tcp  filtered unknown
6006/tcp  filtered X11:6
6101/tcp  filtered backupexec
9091/tcp  filtered xmltec-xmlmail
10243/tcp filtered unknown
22939/tcp filtered unknown
32772/tcp filtered sometimes-rpc7
48080/tcp filtered unknown
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
# Nmap done at Tue Sep 19 15:01:30 2023 -- 1 IP address (1 host up) scanned in 1309.56 seconds
```