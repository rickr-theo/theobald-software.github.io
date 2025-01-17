---
ref: xfa-bw-cube-03
layout: page
title: Laufzeitparameter
description: Laufzeitparameter
product: xtract-for-alteryx
parent: bw-cube
permalink: /:collection/:path
weight: 3
lang: de_DE
---
Verwenden Sie Laufzeitparameter, um Dimensionsfilter und BEx-Variablen dynamisch zur Laufzeit anzupassen.<br>

### Laufzeitparameter erstellen 

1. Um Laufzeitparameter anzulegen und zu bearbeiten, klicken Sie im Hauptfenster der Komponente auf **[Edit Runtime Parameter]**. <br/>
Das Fenster "Edit Runtime Parameters" öffnet sich.<br> 
![Add parameters](/img/content/odp/odp-settings-add-parameters.png){:class="img-responsive"}<br> 
2. Klicken Sie auf **[Add]** (1), um Parameter zu definieren, die als Platzhalter für die Datenfilter verwendet werden können. Die Platzhalter müssen zur Extraktionslaufzeit mit echten Werten befüllt werden.<br>
**Tipp:** Parameter0..-n sind die Standardnamen für die hinzugefügten Parameter. Sie können einen beliebigen Namen eingeben (siehe vorliegendes Beispiel: *"p_MATNR"*).
3. Klicken Sie auf das Drop-Down-Menü (2) und weisen Sie einen der folgenden Datentypen einem Parameter zu. Die Datentypen können, müssen aber nicht mit den SAP-Datentypen übereinstimmen. 
- String: dieser Datentyp kann für jeden Typ der SAP-Felder verwendet werden.
- Number: dieser Datentyp kann nur für numerische SAP-Felder verwendet werden.
- Flag: dieser Datentyp kann nur für SAP-Felder verwendet werden, die einen 'X'&nbsp;(true) oder eine leere Eingabe ''&nbsp;(false) als Eingabewert benötigen. <br>
4. Klicken Sie auf **[OK]** (3), um Ihre Eingabe zu bestätigen.


### Laufzeitparameter zuweisen

Weisen Sie BEx-Variablen oder Dimensionsfiltern Laufzeitparameter zu.

1. Um die erstellten Laufzeitparameter für Variablen zu verwenden, klicken Sie im Hauptfenster der Komponente auf **[Edit Variables]**. Das Fenster "Edit variables..." öffnet sich, siehe [Variablen](./bw-cube-variablen).<br> 
Um die erstellten Laufzeitparameter als Dimensionsfilter zu verwenden, rechtsklicken Sie im Hauptfenster der Komponente auf eine Dimension und wählen Sie **Edit Filter**. Das Fenster "Member Filter" öffnet sich, siehe [Einstellen eines Dimensionsfilters](./bw-cube-extraction-anlegen#einstellen-eines-dimensionsfilters).
2. Wenn Sie Parameter angelegt haben, wird neben den Eingabefeldern ein Parametersymbol angezeigt (4). <br>
Klicken Sie auf die Icons, um zwischen der Eingabe fester Werte und der Eingabe von Parametern zu wechseln.  <br>
![Selection With Parameters](/img/content/bwcube-parameters.png){:class="img-responsive"}
3. Wenn ein Feld auf Parametereingabe umgeschaltet ist, können Sie einen Parameter aus der Drop-Down-Liste (5) auswählen.

