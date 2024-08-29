platform(hackthebox)
system(linux)
time: 17:19
date: 2024-08-28
Challenge: (https://app.hackthebox.com/machines/Editorial)


Scenario: ""

-----
# Recon

0. ip=10.10.11.20 ---> editorial.htb

1. nmap scan1 

- two port open `22,80` let's check the web site

2. nmap scan2 all ports

- nothing new

3. back to website and fuzzing it

- endpoint just `about,uplaod` , and no subdomains

- let's check `upload` endpoint with burp

- url !! SSRF ,let's test it when test it by put localhost address the respon back jpeg image , let's check the image 

- nothing in image , back to url let's brute the port with locathost address by burp intruder 

- we found something in port `5***` 

- he give as path to file after download it it josn file and data i use this `jq` to sort json format 

```bash

cat file | jq

```

- data about api endpint one of them give credit let's use it

# Initial Access

1. the credit for ssh 

- login with `d**:d*********`, get user flag 

2. internal Enum 

- enum .git dir we get new credit 

- su with `p***:******************`

# Privesc

1. with secound user 

- sudo -l good one 

- let's check the script , check info about library info

- we get version by `pip show name_lib` , search for exploit 

- use the exploit 

- get root flag

 


 


-------------------------
# notes: