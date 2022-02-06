---
title: 'Lazy-loading a Singleton Instance'
description: 'Delegate lazy-loading and thread-safety to the JVM.'
excerpt: 'Delegate lazy-loading and thread-safety to the JVM.'
categories: [Development]
tags: [singleton, concurrency, software design patterns, software development, Java]
lang: en
---


A thread-save version of lazy-loading a singleton instance. The instantiation of the singleton is delegated to the JVM which makes this approach fully thread-save -- without explicit synchronization.

```java
public class Singleton {
 
    // class-private singleton constructor
    private Singleton() {}
 
    private static class InstanceHolder {
        private static final Singleton instance = new Singleton();
    }
 
    public static Singleton getInstance() {
        return InstanceHolder.instance;
    }
}
```

Further reading:

+ [Wikipedia, Initialization-on-demand holder idiom](https://en.wikipedia.org/wiki/Initialization-on-demand_holder_idiom)
+ [Thread-save singleton lazy-instantiation](https://en.wikipedia.org/wiki/Double-checked_locking#Usage_in_Java)