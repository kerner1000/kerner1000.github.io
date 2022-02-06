---
title: "Git-friendly refactorings"
excerpt: ""
description: ""
categories: [Development]
tags: []
---


* When using a SCV system, we always try to keep changes atomic. I.e., to fix a bug or add a feature, we try to use exactly one commit ([atomic commit](https://en.wikipedia.org/wiki/Atomic_commit)) that can always be applied (on other branches) or reverted without any side effects.
* Refactorings should be atomic as well.
    * Do not **rename** types or methods on a dedicated branch.