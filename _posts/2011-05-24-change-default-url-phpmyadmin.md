---
title: "Change Default URL for PhpMyAdmin"
excerpt: ""
description: ""
categories: [Blog, Linux]
tags: []
---

---
PhpMyAdmin is reachable via `yourhost.address/phpmyadmin` per default. This is certainly not optimal in terms of security.

Change
```
/etc/phpmyadmin/
```
from
```
Alias /phpmyadmin /usr/share/phpmyadmin
```
to something like
```
Alias /secreturl /usr/share/phpmyadmin
```
After that, reload apache configuration.
```
/etc/init.d/apache2 reload
```