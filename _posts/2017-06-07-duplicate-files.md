---
title: "Find and Remove Duplicate Files"
excerpt: ""
description: ""
categories: [Blog, Linux]
tags: [files and folders, duplicates, pcitures]
---

---
```bash
user@client:~$ fdupes -rdNS some/directory/
```

+ `-r`: recurse into subdirectories
+ `-d`: delete duplicates
+ `-N`: don’t ask which file to keep, just keep the first one (delete all others)
+ `-S`: show file size of duplicates