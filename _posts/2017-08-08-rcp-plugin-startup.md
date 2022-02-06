---
title: 'Startup Instructions for RCP Plug-in'
description: 'Defining startup instructions inside the Plug-in itself.'
excerpt: 'Defining startup instructions inside the Plug-in itself.'
categories: [Development]
tags: [startup, start level, Eclipse RCP]
author: kerner1000
---

---


RCP Plug-in start levels can be defined via a product configuration.

![RCP product configuration](/images/rcp-product-configuration.png)

this is not the best way to do it, if a plug-in is optional, and not necessarily part of the product (which is of course natural for a plug-in).

You can define start levels as well inside the plug-in itself:

Create a file

`META-INF/p2.inf`

with the following Content:

`instructions.configure=setStartLevel(startLevel:4);markStarted(started: true);`