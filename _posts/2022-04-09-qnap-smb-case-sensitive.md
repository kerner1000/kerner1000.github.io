---
title: QNAP SMB Shares are Case Insensitive 
excerpt: "QNAP SMB Shares are Case Insensitive."
description: "QNAP SMB Shares are Case Insensitive."
categories: [Administration]
tags: [QNAP SMB]
---

When mounting shares via SMB, case changes to filenames might not be affective.
To fix this, open the SMB config file, for example with `nano`:

```
nano /etc/smb.conf
```
In nano, you can type `CTRL-W` to find text.
Change 
```
case sensitive = auto
```
to
```
case sensitive = yes
```
save, exit and restart SMB or the QNAP.

References:

* [QNAP Forum](https://forum.qnap.com/viewtopic.php?t=3243)