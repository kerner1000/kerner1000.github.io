---
title: "Git: Selectively Commit Files"
excerpt: ""
description: ""
categories: [Blog]
tags: [Git]


`git commit` commits changes currently in the staging area (changes that have been added using `git add`).

What you usually do is `git add .` or `git commit -am'My commit message'`.

To do a selective commit, e.g. only for a specific file type, use `git add [any wildcard expression]` followed by `git commit`. 

```bash
$ git add *java
$ git commit
```
