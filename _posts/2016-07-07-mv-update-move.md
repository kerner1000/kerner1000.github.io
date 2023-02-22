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

Note that this will override only _newer_ (by timestamp) files. It is not suitable for resuming a failed cp/ move.
For this, you might use

```
rsync -va --append dirA dirB

```
instead. Note that `dirA` and `dirB` need to be present. See [here](https://superuser.com/questions/1174809/linux-copy-only-new-and-larger-files) for more details.