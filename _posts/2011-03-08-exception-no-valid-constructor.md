---
title: "Exception: No Valid Constructor"
excerpt: ""
description: ""
categories: [Blog, Java]
tags: [JavaEE]
---

---
**Problem:**
Deserialization causes Exception.

**Solution:**
+ Make sure all your classes, that are send through the wire, implement `java.io.Serializable`.
+ If your class extends other class(es), *first class in inheritance tree, that does not implement `java.io.Serializable`, must provide a zero-argument standard-constructor!*


