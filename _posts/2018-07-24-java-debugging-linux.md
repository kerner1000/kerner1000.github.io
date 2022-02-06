---
title: 'System Freezes When Debugging Java Applications'
description: 'The graphical user interface freezes/ hangs when debugging Java applications under Linux.'
excerpt: 'The graphical user interface freezes/ hangs when debugging Java applications under Linux.'
categories: [Development]
tags: [x11, Eclipse]
lang: en
---


Acutally, it is only mouse clicks that are not working anymore. The keyboard is still responsive.

**Solution**
Provide the following system property when starting your application, that you want to debug:
`-Dsun.awt.disablegrab=true`

For Eclipse, you can configure your debug configuration as follows:

![eclipse-debugging-arguments](/images/buggyApp.png "Passing Parameters to an Application")

In the *VM arguments:* field, paste `-Dsun.awt.disablegrab=true`, press on *Apply* or *Debug*.

The UI should stay responsive now!

Happy debugging!

PS: this issue has been already reported [here](https://bugs.java.com/view_bug.do?bug_id=6714678).