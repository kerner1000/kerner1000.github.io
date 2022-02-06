---
title: 'Setup Linux Root Server'
description: ''
excerpt: ''
categories: [Development]
tags: [terminal]
lang: en
---


### Log-in via ssh
```
ssh root@ip
```

### Create a user
```
adduser username
```

### Add user to the `sudo` group
```
usermod -aG sudo username
```

### Enable login via ssh key for a user

On a client, [generate a key pair]({{ site.url }}/blog/linux/ssh-key)

then, copy the key to the server:
```
ssh-copy-id -f -i users-key-file_rsa.pub username@ip
```

### [Disable login via password]({{ site.url }}/blog/linux/disable-password-login)

### Enable unattended upgrades
```
apt-get update
apt-get install unattended-upgrades
```
'unattended-upgrades' comes already with a good default configuration. No further steps required.
