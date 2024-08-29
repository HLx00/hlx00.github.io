Subject-----(Linux)------
time: 16:46
date: 2024-08-25
Reference : ()


Scenario: ""
ip ----> 10.10.11.28

-----
# ENUM
1. nmap scan1 `sudo nmap -sCV $ip -T4`
	1. 22,80 open port scan one
2. enum web site
	1.  ffuz = `data,messages,plugins,themes,contact.php
	2. after `صفنه`  in source code i found this in src for img `[http://10.10.11.28/themes/bike/img/velik71-new-logotip.png](view-source:http://10.10.11.28/themes/bike/img/velik71-new-logotip.png)`  let's fuzzing `themes/bike` 
	3. fuzz2= `README.md , version , summary , LICENSE`
	4. in README.md and version i find good info  3.2.0
```md
# WonderCMS bike theme

## Description
Includes animations.

## Author: turboblack

## Preview
![Theme preview](/preview.jpg)

## How to use
1. Login to your WonderCMS website.
2. Click "Settings" and click "Themes".
3. Find theme in the list and click "install".
4. In the "General" tab, select theme to activate it.
```
3. after found CMS , search about exploit
# 
# 
# 
# 
# 
# 
# 
# 
# 


-------------------------
# notes: