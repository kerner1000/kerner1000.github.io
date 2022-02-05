---
title: "SSH Connection by RSA, Disable Password Login"
excerpt: ""
description: ""
categories: [Blog, Linux]
tags: [ssh]
---

---
+ On the client:
```
user@client:~$ ssh-keygen -t rsa -b 4096 -C "user@client"
user@client:~$ ssh-copy-id -i path/to/auth/file/user_rsa.pub user@server
```
+ On the server:
```
user@server:~$ sudo nano /etc/ssh/sshd_config
```
add/ change the following:
```
RSAAuthentication yes
PubkeyAuthentication yes
ChallengeResponseAuthentication no
PasswordAuthentication no
PermitRootLogin no
```
+ .. Finally restart the server:
```
user@server:~$ sudo service ssh restart
```