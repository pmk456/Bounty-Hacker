
# Bounty Hacker WalkThrough
# Deploy Machine
'''
Answer 1 = No Answer Needed
'''
## Scanning Open Ports
'''
Answer 2 = No Answer Needed
# Enumeration
### Scanning For Open Ports

## Found Port 80  Running Apache Server
## Found Port 21 Running FTP
## Found Port 22Running SSH

## Opened FTP Using Command: ftp {your machine ip} and user_name = Anonymous
'''
Found Username With Name Lin in task.txt
Answer 3 = lin
'''
### Also I Found Locks.txt Which May Help Us I Downloaded It Using Get From FTP
### I Got a list of passwords

### Lets Use Hydra To BruteForce SSH
'''
hydra -l lin -V -t 4 -P locks.txt ssh://{your machine ip}
'''
![alt text](https://raw.githubusercontent.com/pmk456/Bounty-Hacker/main/hydra_bf.png)
# Boom I Got The Password
'''
Answer 4 = RedDr4gonSynd1cat3
'''
# Lets SSH Into It
# We Got User Flag Which Is:
'''
THM{CR1M3_SyNd1C4T3}
'''
![alt text](https://raw.githubusercontent.com/pmk456/Bounty-Hacker/main/cat%20user.png)
# Privilage Escalation
### Lets Download Linpeas.sh 
### Started A http server using python and downloaded Linpeas.sh
### When I Runned Linpeas I Have Noticied Something That The /etc/00-header File Was Owned By Root So I Immedietly Looked into it and edited with nano and added cat /root/root.txt 
### When i Loged Out And Login Aganin Boom happened Root.txt was on the login screen
