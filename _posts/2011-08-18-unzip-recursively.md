---
title: "Unzip Archive Recursively"
excerpt: ""
description: ""
categories: [Administration]
tags: [zip]
---

---
Sometimes you want to extract all files from an archive recursively, for example an ear, that means, extract also all archives inside the archive:
 
 For an `ear`, `war` or `jar`, you can do so like this:
 
 ```
 find -name "*.*ar" -exec unzip {} ;
 ```
 