---
title: Default Permissions for Default Folders on Mac  
excerpt: "What are the default permissions for default folders in a users home directory?"
description: "What are the default permissions for default folders in a users home directory?"
categories: [Administration]
tags: [files and folders, mac]
---

A freshly created user comes with the following files and folders in the home directory:

```
-MacBook-Pro kristina % ls -lha
total 0
drwxr-x---+ 11 kristina  staff   352B Feb  2 19:48 .
drwxr-xr-x   7 root      admin   224B Feb 11 13:28 ..
-rw-------   1 kristina  staff     3B Feb  2 19:48 .CFUserTextEncoding
drwx------+  3 kristina  staff    96B Feb  2 19:48 Desktop
drwx------+  3 kristina  staff    96B Feb  2 19:48 Documents
drwx------+  3 kristina  staff    96B Feb  2 19:48 Downloads
drwx------+ 31 kristina  staff   992B Feb  2 19:49 Library
drwx------   3 kristina  staff    96B Feb  2 19:48 Movies
drwx------+  3 kristina  staff    96B Feb  2 19:48 Music
drwx------+  3 kristina  staff    96B Feb  2 19:48 Pictures
drwxr-xr-x+  4 kristina  staff   128B Feb  2 19:48 Public
```

Another listing, this time only folders but with numerical permissions as well:

```
[..]-MacBook-Pro kristina % ls -l | awk '{k=0;for(i=0;i<=8;i++)k+=((substr($1,i+2,1)~/[rwx]/) \
             *2^(8-i));if(k)printf("%0o ",k);print}'
total 0
700 drwx------+  3 kristina  staff   96 Feb  2 19:48 Desktop
700 drwx------+  3 kristina  staff   96 Feb  2 19:48 Documents
700 drwx------+  3 kristina  staff   96 Feb  2 19:48 Downloads
700 drwx------+ 31 kristina  staff  992 Feb  2 19:49 Library
700 drwx------   3 kristina  staff   96 Feb  2 19:48 Movies
700 drwx------+  3 kristina  staff   96 Feb  2 19:48 Music
700 drwx------+  3 kristina  staff   96 Feb  2 19:48 Pictures
755 drwxr-xr-x+  4 kristina  staff  128 Feb  2 19:48 Public
```