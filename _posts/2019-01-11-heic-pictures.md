---
title: "Convert *.heic* files to *.jpg*"
excerpt: ""
description: ""
categories: [Media]
tags: [files and folders, pictures, terminal]
---

---
```bash
sudo apt-get install libheif-examples
for file in *.heic; do heif-convert $file ${file/%.heic/_converted.jpg}; done
```
If sucessful, delete all `heic` files:
```bash
rm *.heic
```
