---
title: "Exception: No Valid Constructor"
excerpt: ""
description: ""
categories: [Blog, Java]
tags: [JavaEE]
---

---
**Problem:**
Pushing to sourceforge.net project is not possible. It fails with follwing error message:

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
[Sourcceforge Wiki](https://sourceforge.net/apps/trac/sourceforge/wiki/Git#Access)
