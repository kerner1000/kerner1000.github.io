---
title: 'New Line Characters'
description: ''
excerpt: ''
categories: [Blog, Java, Linux]
tags: []
lang: en
---

The **Carriage Return** (`CR`) character (`0x0D`, `\r`) moves the cursor to the beginning of the line without advancing to the next line. This character is used as a new line character in Commodore and Early Macintosh operating systems (OS-9 and earlier).

The **Line Feed** (`LF`) character (`0x0A`, `\n`) moves the cursor down to the next line without returning to the beginning of the line. This character is used as a new line character in UNIX based systems (Linux, Mac OSX, etc)

The **End of Line** (`EOL`) sequence (`0x0D 0x0A`, `\r\n`) is actually two ASCII characters, a combination of the CR and LF characters. It moves the cursor both down to the next line and to the beginning of that line. This character is used as a new line character in most other non-Unix operating systems including Microsoft Windows, Symbian OS and others.

[Source](https://knowledge.ni.com/KnowledgeArticleDetails?id=kA00Z0000019KZDSA2)