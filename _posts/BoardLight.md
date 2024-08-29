Hack the box
Subject-----(Linux)------
time: 06:42
date: 2024-08-26
Reference : (https://app.hackthebox.com/machines/BoardLight)


Scenario: ""
ip=10.10.11.11 --> board.htb 

1. nmap scan

- 22,80 open port

- let's check web site 

2. i use fuzzin for endpoint and i dont find any thing 

3. i use fuzzing for subdomain and i found this `crm.board.htb` 

- open it is login page create by CMS name is `dolibarr 17.0.0`

- try default credit and search for exploit

- `a****:a****` login as admin

4. get revers shell i find this exploit https://github.com/nikn0laty/Exploit-for-Dolibarr-17.0.0-CVE-2023-30253   

- let's try it , i get reverse shell

5. internal enum

-  use linpeas.sh

- after enum i get `dolibarrowner:serverfun2$2023!!` for mysql in config php file enum for ever after `sfnaa` this password for ssh for user in home dir name is larissa 

6. get root

- i run linpease.sh , check SUID i find `linux-gnu-x86_64-0.23.1` search about exploit 

- https://github.com/MaherAzzouzi/CVE-2022-37706-LPE-exploit/blob/main/README.md -----> get root.txt


-------------------------
# notes:
check Version 