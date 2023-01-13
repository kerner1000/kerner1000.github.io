---
title: "Java(FX), Codesiging and the App Store"
excerpt: "The Martyrium of codesigning Java Apps."
description: "The Martyrium of codesigning Java Apps."
categories: [Development]
tags: [Java, JavaFX, codesign, Mac]
---


## Troubleshooting codesigning problems

### Finding the problem

```
codesign --verify DrKodi.app
```

```
codesign -d --verbose=4 DrKodi.app
```
