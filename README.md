# [Gobuster: The Basics | TryHackMe Write-Up](https://tryhackme.com/room/gobusterthebasics)
This room focuses on an introduction to Gobuster, an offensive security tool used for enumeration.


## Task 1 Introduction
No answer needed
## Task 2 Environment and Setup
![image](https://github.com/user-attachments/assets/f50e6c21-192b-495d-95ac-7c0517d8fec1)
![image](https://github.com/user-attachments/assets/3413dfb5-652d-4199-bad8-ffebe78691e0)
No answer needed
## Task 3 Gobuster: Introduction
What flag do we use to specify the target URL?
> -u

What command do we use for the subdomain enumeration mode?
> dns
## Task 4 Use Case: Directory and File Enumeration
Which flag do we have to add to our command to skip the TLS verification? Enter the long flag notation.
> --no-tls-validation

Enumerate the directories of www.offensivetools.thm. Which directory catches your attention?

```
gobuster dir -u 10.10.35.100 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -t 50
```

![image](https://github.com/user-attachments/assets/8864eed8-ed21-4d07-ac24-f9d9a6bb3bee)
> secret

Continue enumerating the directory found in question 2. You will find an interesting file there with a .js extension. What is the flag found in this file?

```
gobuster dir -u 10.10.35.100/secret -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -x js -t 50
gobuster dir -u 10.10.35.100/secret/content -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -x js -t 50

```






