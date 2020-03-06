---
ref: xtract-is-01
layout: page
title: Xtract IS
description: Xtract IS
product: xtract-is
parent: home
childidentifier: xtract-is
permalink: /:collection/:path
weight: 1
lang: de_DE
old_url: /Xtract-IS-DE/
---
### Architektur

Xtract IS ist ein Plug-In für die SQL-Server-Integration-Services (SSIS). Xtract IS kann nicht außerhalb von SSIS verwendet werden, <br>
sodass eine SQL Server Lizenz notwendig ist, auch bei nicht verwendeter SQL Server Datenbank. 

Die Xtract IS Komponentensuite bietet Ihnen insgesamt 10 unterschiedliche Komponenten für die SQL-Server-Integration-Services an.

Somit bietet die Xtract IS Komponentensuite Ihnen die komplette Bandbreite der Datenextraktion für unterschiedliche SAP-Objekte. 

![XIS-Architecture](/img/content/xis/architectures_xis_neu.png){:class="img-responsive"}

### Verwendung der Komponenten
In der unten stehenden Übersicht sehen Sie, bei welcher Komponente Lese (R),- und Schreibrechte (W) zur Verfügung stehen. 

Die benötigte Lizenz für die Nutzung unterschiedlicher Komponenten im SAP ERP sowie SAP BW sind ebenfalls der Tabelle zu entnehmen.

| Komponente | ERP | BW | Enterprise <br> Lizenz | Ultimate <br> Lizenz  |
|-------------|-----|----|:--|:--|
| Table       | R   | R  | X                  | X                |
| Table Join  | R   | R  |                    | X                |
| BAPI        | R/W  | R/W | X                  | X                |
| Query       | R   |    | X                  | X                |
| ABAP Report | R   |    |                    | X                |
| DeltaQ      | R   | R  |                    | X                |
| BW Cube     |     | R  | X                  | X                |
| Hierarchy   |     | R  |                    | X                |
| OHS         |     | R  |                    | X                |
| BW Loader   |     | W  |                    | X                | 


Die Online-Hilfe zu Xtract IS besteht aus den folgenden Abschnitten:

{% include _content/table-of-contents.html parent="xtract-is" collection=site.de %}
