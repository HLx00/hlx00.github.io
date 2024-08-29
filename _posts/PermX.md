platform (hackthebox)
Subject-----(linux)------
time: 22:52
date: 2024-08-27
Challenge: (https://app.hackthebox.com/machines/PermX)


Scenario: ""

-----
ip = 10.10.11.23 permx.htb

1. nmap scan 
- 22,80 open port only
2. check the web site 
- fuzzing and find `img,js,lib,css`
- fuzzing subdomains and find `lms`
3. check lms subdomain
- login page LMS name is `chamilo` i think version 1 
- and find email for admin `admin@permx.htb` and name is`Davis Miller`
- let's search for any exploit to bypass login page 
- i found this `https://github.com/m3m0o/chamilo-lms-unauthenticated-big-upload-rce-poc`  i use default shells in exploit 
4. we get shell !!
- after eunm i find credit in config php file `chamilo:03F6lY3uXAP2bkW8` for mysql and i find hashs
- after fu***ng with hash , is db pass for shh 
- we get user flag
5. get root
-  `sudo -l` ---> yep is so ez
- this file acl.sh is run as root without password let's check it the script give perm for any file 
- get root 
```bash
>>ln -s /etc/passwd passwd
>>sudo /opt/acl.sh mtz rwx /home/mtz/passwd
>>nano passwd # remove x for root to Switch to root with out password
```




-------------------------
# notes: