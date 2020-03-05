---
ref: xfa-table-02
layout: page
title: Table Joins
description: Table Joins
product: xtract-for-alteryx
parent: table
permalink: /:collection/:path
weight: 2
lang: de_DE
---

Voraussetzung für die Nutzung ist die Installation Funktionsbausteins [Z_THEO_READ_TABLE](../sap-customizing) in SAP.

Unter dem Tab *Joins* können in der Komponente ab Version 4.x Tabellen-Joins definiert werden.

Die *Joins* Funktion dient dazu, mehrere Tabellen (und Views) auf SAP-Seite zusammenzufassen.  <br>
Mögliche Szenarien dafür wären, Tabellen für Kopf- und Positionsdaten (z.B. einer Bestellung oder Rechnung) oder Tabellen für Stammdaten und Texte (z.B. eines Materials) zu joinen. <br>
Dazu wird dynamisch der entsprechende SQL-Befehl generiert und auf dem SAP-Server ausgeführt. <br>

<div class="alert alert-info">
  <i class="fas fa-info-circle"></i> <strong>Note:</strong> Joins von Cluster- und Pool-Tabellen werden nicht unterstützt, können aber als Einzeltabellen extrahiert werden.
</div>

Zum Anlegen von Tabellen-Joins beachten Sie folgende Schritte:

**Tabellen definieren**

Im Beispiel sollen die Tabellen MARA und MAKT gejoined werden. Fügen Sie hierfür die beiden Tabellen über den *Tables* Dialog hinzu. 

![Table-Join-Tabellen](/img/content/join_tabellen_auswählen.png){:class="img-responsive"}

**Felder selektieren**

Selektieren Sie anschließend die gewünschten Felder in den Tabellen. Bei der Selektion stehen die unter [Tabellen und Felder](./tabellen_und_felder) erläuterten Aggregierungsfunktionen zur Verfügung. 

Hier ein Beispiel, um die Anzahl des Sprachen-Felds (SPRAS) in der Tabelle MAKT zurückzugeben.   

![Table-Join-Felder](/img/content/join_felder_auswählen.png){:class="img-responsive"}

**Verknüpfungen definieren**

Wechselt man nun in den *Joins* Dialog ist bereits eine Inner Join Verknüpfung vordefiniert. Die Unterscheidung von *Inner Joins* und *Outer Joins* ist [hier](https://help.sap.com/doc/saphelp_tm80/8.0/de-DE/cf/21ec77446011d189700000e8322d00/content.htm?no_cache=true) erläutert. <br>
Für die Details klicken Sie auf das Stift-Symbol. Im Beispiel wurde die Tabelle MARA (Linke Tabelle) mit der Tabelle MAKT (Rechte Tabelle) anhand der Felder MATNR und MANDT mit dem Join-Typ "Inner" zusammengefügt. <br>
Bei den angebotenen Einstellungen und Verknüpfungen handelt es sich lediglich um Vorschlagwerte, alle Bestandteile, d.h. *Left Table*, *Right Table*, *Join Type* und *Join Mapping* lassen sich nachträglich ändern. <br>
- Um weitere Feldverknüpfungen hinzuzufügen, klicken Sie auf *Add*. 
- Bestehende Verknüpfungen lassen sich mit *Remove* (Mülltonnen-Symbol) entfernen. 
- Weitere Tabellen lassen sich über den *Tables and Fields* Dialog hinzufügen. Wir empfehlen grundsätzlich, nicht mehr als fünf Tabellen miteinander zu joinen.    

![Table-Join-Verknüpfungen](/img/content/join_verknüpfungen_01.png){:class="img-responsive"}

Beispiel eines Joins mit einer dritten Tabelle:

![Table-Join-Verknüpfungen2](/img/content/join_verknüpfungen_02.png){:class="img-responsive"}

![Table-Join-Verknüpfungen3](/img/content/join_verknüpfungen_03.png){:class="img-responsive"}

   
**Auto-Mapping Funktion**

Über den Button *Auto-map* wird das bestehende Mapping gelöscht und ein erneutes Mapping gleich lautender Felder durchgeführt. Dieser Schritt ist optional und kann beispielsweise erforderlich sein, wenn die Referenztabelle erst am Schluss hinzugefügt wird.     

![Table-Join-Automapping](/img/content/join_automap.png){:class="img-responsive"}


 
 
  
