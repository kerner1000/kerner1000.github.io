---
title: 'MySQL won’t start automatically during system startup'
description: ''
excerpt: ''
categories: [Administration]
tags: []
---


MySQL won’t start automatically during system startup
P: The MySQL service does not automatically start during system startup.
A:
Purge and redo startup scripts:
sudo update-rc.d -f mysql remove
sudo update-rc.d mysql defaults
1
2
sudo update-rc.d -f mysql remove
sudo update-rc.d mysql defaults
Change bind-address to 0.0.0.0:
sudo nano /etc/mysql/my.cnf
1
sudo nano /etc/mysql/my.cnf
Find bind-address = 127.0.0.1 and change it to bind-address = 0.0.0.0
Check /etc/init/mysql.override: This file might override your startup settings. In case it looks like this
$ less /etc/init/mysql.override
manual
Execute the following:
echo auto | sudo tee /etc/init/mysql.override
1
echo auto | sudo tee /etc/init/mysql.override
Done.