---
title: 'Disable Password Login'
description: ''
excerpt: ''
categories: [Administration]
tags: [ssh]
lang: en
---


### Make a backup of the current ssh configuration

+ `cd /etc/ssh/`
+ `cp sshd_config sshd_config.bak`

Edit `/etc/ssh/sshd_confg`:
```bash
# diff /etc/ssh/sshd_config /etc/ssh/sshd_config.bak 
< PasswordAuthentication no
---
> #PasswordAuthentication yes
```

### Restart the ssh server
```
sudo service sshd restart
```