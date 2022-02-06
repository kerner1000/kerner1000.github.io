---
title: "List Top 10 Largest Files and Directories"
description: "Print a list of the top 10 largest files and directories."
excerpt: "Print a list of the top 10 largest files and directories."
categories: [Administration]
tags: [files and folders, terminal]

---

```bash
du -hsx * 2>/dev/null | sort -rh | head -10
```
Note that only files and directories will be considered, for which the current user has read-permissions. There will be no error messages.

[source](http://www.cyberciti.biz/faq/how-do-i-find-the-largest-filesdirectories-on-a-linuxunixbsd-filesystem/)