---
title: "Message-Driven Beans, Message not send / received"
excerpt: ""
description: ""
categories: [Blog, Java]
tags: [JavaEE]
---

---
**Problem:**
When sending a message via JMS (transactions enabled) this message is not received by other MessageListener.
```Java
QueueConnection queueConnection = queueConnectionFactory.createQueueConnection();
Session session = queueConnection.createSession(true, 0);
MessageProducer messageProducer = session.createProducer(queue);
ObjectMessage m = session.createObjectMessage(new ObjectMessage());
messageProducer.send(m);
session.close();
```
**Solution:**
Add an additional `session.commit();` before closing the session.

Further information:
`session.close()` will *not* implicitly invoke `session.commit()`!
This is probably due to the fact that `session.commit()` throws an exception if this session was created without transaction support.
e.g.
```Java
Session session = queueConnection.createSession(false, Session.AUTO_ACKNOWLEDGE);
```

**Note:**
This behavior was observed on JBoss AS 6.
As far as I know, parameters to `createSession()` method should be ignored according to the specifications.
But such implementations are certainly vendor specific.

