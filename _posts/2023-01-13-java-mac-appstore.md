---
title: "Codesiging Java apps for the Apple App Store"
excerpt: "The Martyrium of codesigning Java Apps for MacOS."
description: "The Martyrium of codesigning Java Apps for MacOS."
categories: [Development]
tags: [Java, JavaFX, codesign, Mac]
---

## Tell Apple about your App

1. Register as a developer at [developer.apple.com](https://developer.apple.com/).

2. Go to [developer.apple.com/account/resources/certificates/list](https://developer.apple.com/account/resources/certificates/list)
	and register a new identifier for the app.

	![localImage](/images/Apple-Developer-Certificates-Identifiers-Profies.png)

3. Go to [appstoreconnect.apple.com/apps](https://appstoreconnect.apple.com/apps)
	and register a new App with the created identifier.

	![localImage](/images/Apple-Developer-new-App.png)

4. Go to [appstoreconnect.apple.com/access/api](https://appstoreconnect.apple.com/access/api)
	and create a developer API key.

	![localImage](/images/Apple-Developer-App-Store-Connect-API-Keys.png)

	You will need the "Issuer ID" and the "KEY ID" later for the notarization.

## Codesign your App



## Notarize your App

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