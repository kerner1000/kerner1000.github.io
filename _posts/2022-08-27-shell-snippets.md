---
title: "Shell Snippets"
excerpt: "Shell Copy&Pase-Snippets."
description: "Shell Copy&Pase-Snippets."
categories: [Development, Administration]
tags: [Bash, Shell]
---

Folders and files need to have different umask bits to have the 'same' rights.
Therefore, we need to manually set the right mods:

```bash
find /verzeichnis/ -type d -exec chmod 755 {} +
find /verzeichnis/ -type f -exec chmod 644 {} +
``` 