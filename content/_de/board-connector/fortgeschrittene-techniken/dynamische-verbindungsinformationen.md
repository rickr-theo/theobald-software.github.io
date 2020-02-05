---
ref: bc-advanced-techniques-03
layout: page
title: Dynamische Verbindungsinformationen
description: Dynamische Verbindungsinformationen
product: board-connector
parent: fortgeschrittene-techniken
permalink: /:collection/:path
weight: 3
lang: de_DE
old_url: /BOARD-Connector-DE/default.aspx?pageid=dynamische-verbindungsinformationen
---

Analog zu den System- und benutzerdefinierten Parametern können auch die Verbindungseinstellungen zum SAP dynamisch über die URL geändert werden. Das geschieht über den dritten Tabreiter im Run-Dialog.


![Run-Extraction-Connection-Parameters](/img/content/Run-Extraction-Connection-Parameters.png){:class="img-responsive"}



Das Beispiel zeigt die Überschreibung der Verbindungssprache mit folgender URL:

```
http://localhost:8085/?name=plants&lang=DE
```
