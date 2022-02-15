---
title: "Push to SourceForge failed"
excerpt: ""
description: ""
categories: [Development]
tags: [Java]
---

---
**Problem:**
Pushing to SourceForge.net project is not possible. It fails with follwing error message:

```
error: insufficient permission for adding an object to repository database ./objects
fatal: failed to write object
```
(or similar)

Solution:
Change your ssh username to `[username],[linux-projectname]`, e.g.
```
ssh://hans,hans-project@hans-project.git.sourceforge.net/gitroot/hans-project/hans-project
```
**Further information:**
[SourceForge.net Wiki](https://sourceforge.net/apps/trac/sourceforge/wiki/Git#Access)
