---
ref: xtract-universal-01
layout: page
title: Xtract Universal
description: Xtract Universal
product: xtract-universal
parent: home
childidentifier: xtract-universal
permalink: /:collection/:path
weight: 1
lang: de_DE
old_url: /Xtract-Universal-DE/
---

Willkommen in der Online Help von Xtract Universal. 

Xtract Universal ist ein SAP Connector und ermöglicht es, Datenobjekte aus SAP zu extrahieren und an beliebige Zielumgebungen zu liefern.

### Architektur

![XU-architecture](/img/content/xu/theobald-software-graphic.png)

In der unteren Übersicht finden Sie, welche Komponente für die Datenextraktion aus einem SAP ERP- bzw. BW-System verwendet werden können. 

| Komponente   | ERP | BW |
|-------------|:---:|:--:|
| Table       | X   | X  |
| Table Join  | X   | X  |
| BAPI        | X   | X  |
| Query       | X   |    |
| ABAP Report | X   |    |
| DeltaQ      | X   | X  |
| BW Cube     |     | X  |
| Hierarchy   |     | X  |
| OHS         |     | X  |
| ODP         | X   | X |

Hier finden Sie die folgenden Abschnitt:

{% include _content/table-of-contents.html parent=page.childidentifier collection=site.de %}
