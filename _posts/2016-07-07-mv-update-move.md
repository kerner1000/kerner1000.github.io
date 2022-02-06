---
title: 'mv: do not override destination file that is newer than source file (update move)'
description: ''
excerpt: ''
categories: [Administration, Media]
tags: [terminal]
lang: en
---

`mv` does not support the update option, unlike `rsync` and `cp`. If your version of coreutils does support it, using cp (followed by rm) is the easiest way to perform an update move operation:

```
$ cp -avu * [destination]
$ rm -rf *
```