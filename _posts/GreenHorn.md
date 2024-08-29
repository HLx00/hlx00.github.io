Platform--------->> hack the box
Subject-----(machine)------
time: 05:16
date: 2024-08-25
Reference : (https://app.hackthebox.com/machines/GreenHorn)

ip=10.10.11.25 -->greenhorn.htb
Scenario: ""

-----
# ENUM 
1. nmap scan `sudo nmap -sCV $ip -T4`
	1. 22,80,3000 open port
2. fuzz the web site 
	1.  images,docs,files,data --> 403
3. in url web site i think is vuln by LFI `http://greenhorn.htb/?file=welcome-to-greenhorn` i test it manual  
4. check the source code if found login page and create by CMS name is pluck 4.7.18 let's search for exploit for it
5. port 3000 for service let's eunm it 
	1. after fuzz it we found this endpoint `/explore`
	2. we found **repo git for admin !!!!** we have access for source code for we site let's check it 
	3. after reop enum we find hash password crack it --->iloveyou1
# Initial access
1. login to CMS , let's try to get revers shell 
2. in module we upload php rshell after zipped it 
3. we get shell www-data
4. su to user junior by password ---> iloveyou1
5. get user flag
# Privesc
1. enum user junior
	1. get pdf file
2. ![[Pasted image 20240825064820.png]]
3. Extract the image in pdf  ![[Pasted image 20240825065122.png]] the images is blurred
4. to solve this problem we install this tools `git clone https://github.com/spipm/Depix`
5. ![[Pasted image 20240825070114.png]]
6. the Results ![[Pasted image 20240825070438.png]] 
7. root password `sidefromsidetheothersidesidefromsidetheotherside` 

-------------------------
# notes:
### A new subject how to fax blurred image 