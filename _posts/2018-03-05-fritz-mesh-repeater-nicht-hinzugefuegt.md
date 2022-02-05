---
title: "WLAN Repeater wird nicht ins Mesh eingebunden"
excerpt: "Der WLAN Repeater verbindet sich zwar mit dem WLAN, das Mesh Symbol wird aber nicht angezeigt."
description: "Der WLAN Repeater verbindet sich zwar mit dem WLAN, das Mesh Symbol wird aber nicht angezeigt."
categories: [Blog]
tags: [Fritz!, mesh, wlan]
lang: de
---


Insbesondere wenn man einen Repeater ins Mesh aufnehmen möchte, der der FritzBox schon bekannt ist, also schon mal verbunden war, kann es vorkommen, dass die WLAN-Verbindung zwar hergestellt wird, der Repeater aber nicht ins Mesh aufgenommen wird (Mesh Symbol wird nicht angezeigt).

Wenn der Repeater bereits erfolgreich ins WLAN-Netz aufgenommen wurde, kann man kann die Mesh Konfiguration einfach manuell anstoßen:

Dazu muss zuerst der WPS Button an der FritzBox gedrückt werden (kurz!), innerhalb von zwei Minuten dann der WPS Button des Repeaters (kurz!).

**Wichtig:** Der Repeater wird *nicht* blinken oder sonst wie eine Rückmeldung geben! Geht man in die Netzwerkübersicht der Weboberfläche des Routers, sollte hier aber nun das Mesh-Symbol am Router angezeigt werden.

![Mesh aktiv](/images/310-mesh-nicht-aktiv2-t.png  "Mesh nicht aktiv") ![Mesh aktiv](/images/310-mesh-aktiv-t.png  "Mesh aktiv")

**Wichtig:** Das Anstoßen des WPS muss über die Tasten erfolgen! Probiert man das gleiche über die Weboberfläche der FritzBox/ des Repeaters, wird das ganze nicht klappen!

***Repeater Reihenschaltung***

Das Gleiche gilt prinzipiell auch, wenn der Zugriffspunkt für einen weiteren Repeater nicht die Fritzbox selbst ist, sondern ein anderer Repeater.
0. Repeater verbinden: Zunächst den WPS Knopf des Repeaters drücken, der schon im Mesh eingebunden ist. Dann den WPS Knopf des neuen Repeaters.
0. Mesh aktivieren: Zunächst den WPS Knopf der FritzBox drücken, dann den WPS Knopf des neuen Repeaters. Wieder wie oben, der Repeater gibt keine Rückmeldung, also nicht doppelt drücken!

In der Weboberfläche der Box sollte der neue Repeater jetzt mit Mesh Symbol angezeigt werden.

**Achtung:** Falls die FritzBox keinen extra WPS Knopf hat, muss der WLAN Button gedrückt werden. Und zwar etwas länger, da sich sonst nur WLAN abschaltet.

Im Einsatz: [FritzBox 7580](http://amzn.to/2oPsIpM), [Repeater 1750E](http://amzn.to/2FjLOeF),  [Repeater 1160](http://amzn.to/2I2LOkZ) sowie [Repeater 310](http://amzn.to/2D0rlcN).

Mehr dazu auch [hier](https://service.avm.de/help/de/FRITZ-Box-7580/017p1/hilfe_connect_push).













