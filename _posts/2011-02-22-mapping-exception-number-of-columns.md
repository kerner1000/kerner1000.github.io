---
title: "org.hibernate.MappingException: property mapping has wrong number of columns"
excerpt: "When deploying a persistence unit (jar, jar within ear), MappingException is thrown."
description: "When deploying a persistence unit (jar, jar within ear), MappingException is thrown."
categories: [Development]
tags: [Hibernate, Java]
lang: en
---


**Solution:**
Check data types of your Entity Bean, and change any `Object` to something else, e.g. `String`.

Hibernate does not know how to map `Object` to a valid database type. Do not use Object fields within your Entity Beans.