---
title: "NoClassDefFoundError when deploying EAR"
excerpt: "When deploying an EAR (enterprise archive file) to an application server like JBOSS, java.lang.NoClassDefFoundError is thrown."
description: "When deploying an EAR (enterprise archive file) to an application server like JBOSS, java.lang.NoClassDefFoundError is thrown."
categories: [Development]
tags: [Java]
---


**Solution**: Fix your EAR package structure:

Wrong             |  Right
:-------------------------:|:-------------------------:
![Wrong](/images/ear-package-structure.png)  |  ![Right](/images/ear-package-structure.21.png)

![Eclipse project setup](/images/javaee.module.dependencies.png)

Further information:

0. All projects/ files have been created with Eclipse
0. `application.ear`: Exported as "Enterprise Application Project"
0. `app-ejb.jar`: Exported as "Enterprise Java Beans Project"
0. `app-web.war`: Exported as "Dynamic Web Project"
0. `app-shared.jar`: Exported as "Java Project", that contains classes that are used by more than one of the sub-projects. Can also be a third party jar-File with library classes.
0. Exception occurs, since `app-web.war` or `app-ejb.jar` may be deployed just before `app-shared.jar` has been deployed. A workaround for that would be to first deploy `app-shared.jar` separately and remove it from your enterprise application compilation.