---
title: "Codesiging Java apps for the Apple App Store"
excerpt: "The Martyrium of codesigning Java Apps for MacOS."
description: "The Martyrium of codesigning Java Apps for MacOS."
categories: [Development]
tags: [Java, JavaFX, codesign, Mac]
---




## Troubleshooting codesigning problems

### Finding the problem

```
codesign --verify DrKodi.app
```

To verify that the app is signed, the following command provides information about the signing status of the app:
```
codesign -d --verbose=4 DrKodi.app
```

To check whether an application can be launched when Gatekeeper is enabled, use the spctl command:
```
spctl --assess --verbose=4 DrKodi.app
DrKodi.app: rejected
source=no usable signature
```

If you leave off the --verbose tag, and it does not print any output, indicates 'success'.

Sources:
- https://docs.oracle.com/javase/7/docs/technotes/guides/jweb/packagingAppsForMac.html