---
ref: xu-tableau-03
layout: page
title: Verlinken einer BEx-Query mit einer BW-Hierarchie
description: Verlinken einer BEx-Query mit einer BW-Hierarchie
product: xtract-universal
parent: tableau
permalink: /:collection/:path
weight: 3
lang: de_DE
old_url: /Xtract-Universal-DE/default.aspx?pageid=verlinken-bex-query-mit-bw-hierarchie
---

In diesem Beispiel extrahieren wir eine BEx-Query und eine BW-Hierarchie und erstellen eine Beziehung in Tableau, um die beiden Extraktionen zu verlinken. 

**Schritt 1**: Eine BEx-Query-Extraction anlegen.

![XU-Tableau-BExQuery](/img/content/XU-Tableau-BExQuery.png){:class="img-responsive"}

Die Extraktion hat die folgenden General Settings:

![XU-Tableau-BExQuery-Settings](/img/content/XU-Tableau-BExQuery-Settings.png){:class="img-responsive"}

Für weitere Informationen siehe [BW InfoCubes und BEx Queries](../../bw-infocubes-und-bex-queries).

**Schritt 2**: Eine BW-Hierarchie-Extraktion anlegen.

![XU-Tableau-Hierarchy](/img/content/XU-Tableau-Hierarchy.png){:class="img-responsive"}

Die Extraktion hat die folgenden General Settings. Hier wird die Option *Natural representation* gewählt. 

![XU-Tableau-Hierarchy-Settings](/img/content/XU-Tableau-Hierarchy-Settings.png){:class="img-responsive"}

Für weitere Informationen siehe [BW Hierarchien](../../bw-hierarchien).


**Schritt 3**: Beide Extraktionen in Tableau laden und eine Beziehung dazwischen erstellen.

![Tableau-BExQuery-Datasource](/img/content/Tableau-BExQuery-Datasource.png){:class="img-responsive"}

![Tableau-BWHierarchy-Datasource](/img/content/Tableau-BWHierarchy-Datasource.png){:class="img-responsive"}

Wir erstellen eine Beziehung zwischen beiden Extraktionen, in dem wir die Felder Sold to *party key* (bexquery) und *Node Name* (bwhierarchy) verlinken.

Wählen Sie aus dem Menü Data -> *Edit Relationships*.<br>
Wählen Sie *Custom* und klicken Sie auf Add.<br>
Wählen Sie *Node Name* als das primary field und *Sold to party Key* als das secondary field.<br>
Klicken Sie auf OK.

![Tableau-Edit-Relationships](/img/content/Tableau-Edit-Relationships.png){:class="img-responsive"}

Die beiden Extraktionen sind nun verlinkt und Sie können Daten aus beiden Extraktionen in einem einzigen Tableau-Sheet verwenden. 

![Tableau-Linked-Data-Sources](/img/content/Tableau-Linked-Data-Sources.png){:class="img-responsive"}

Für weitere Informationen über Beziehungen in Tableau siehe [Tableau Online Help](https://www.tableau.com/support/online). 
