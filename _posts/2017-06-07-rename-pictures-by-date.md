---
title: "Rename Pictures by Date"
excerpt: ""
description: ""
categories: [Blog, Linux]
tags: [files and folders, rename, pictures]
---

---
```bash
exiv2 rename -Fk *
```

+ `-F`: Do not override files. Append '_1' ('_2', ...) to the name of the new file.
+ `-k`: Preserve file timestampls.