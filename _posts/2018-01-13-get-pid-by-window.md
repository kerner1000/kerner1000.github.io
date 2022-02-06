---
title: "Get PID by Window"
excerpt: "Get the PID of a Process by it's Window"
description: "Get the PID of a Process by it's Window"
categories: [Development]
tags: [terminal]
---


Get the PID of a process by it's window:

```bash
$ xprop | awk '/PID/ {print $3}'
```

This will change your mouse cursor to a cross. Click on the window and get the PID printed on the terminal.