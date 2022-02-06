---
title: "Change @author default value"
excerpt: ""
description: ""
categories: [Development]
tags: [Eclipse, template variable]
---

Add user

When adding a comment to a class, the `@author` element is added automatically. The author name is stored in the Template Variable `{$user}` and defaults to the currently logged in user name. To override that, edit `eclipse.ini`. Add
```
-Duser.name=My Name
```
It will look something like that:
```
[..]
-Dosgi.requiredJavaVersion=1.8
-Xms256m
-Xmx1024m
--add-modules=ALL-SYSTEM
-Duser.name=My Name
```
There are other variables you can define like that, e.g. `-Duser.language=en` or  `-Duser.region=US`.

Find more infos [here](https://stackoverflow.com/questions/1131712/how-to-set-the-eclipse-date-variable-format).

