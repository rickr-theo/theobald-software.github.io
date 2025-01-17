---
ref: xtract-for-alteryx-06
layout: page
title: BW Cube
description: BW Cube
product: xtract-for-alteryx
parent: xtract-for-alteryx
childidentifier: bw-cube
permalink: /:collection/:path
weight: 6
lang: de_DE
progressstate: 5
---
Der folgende Abschnitt beschreibt die Funktion der Xtract Cube Komponente in Xtract for Alteryx. <br>
Die Xtract Cube Komponente kann verwendet werden, um die Daten aus SAP BW (BEx) Queries und InfoProviders (z.B. InfoCubes) zu extrahieren. 
Die Xtract Cube Komponente unterstützt zwei Extraktionsmodi: MDX und BICS (beta).

{: .box-tip }
**Tipp:** Grundlagen zum Produkt sind im Abschnitt [Erste Schritte mit Xtract for Alteryx](./erste-schritte) beschrieben.

### BW Cube verwenden
1. Ziehen Sie die "Xtract BW Cube" Komponente per drag & drop auf Ihren Alteryx-Workflow.
2. Wählen Sie eine SAP-Verbindung, navigieren Sie zur gewählten Extraktion und klicken Sie auf **[Edit]**. Das Hauptfenster der Komponente öffnet sich.


### Funktionsübersicht
Das Hauptfenster der BW Cube Komponente besteht aus zwei Unterabschnitten und einigen  Schaltflächen:

- Cube orQuery
- Preview
![Cube Extractor](/img/content/xfa/xfa-cube-query-overview.png){:class="img-responsive"}

#### Cube or Query
Im Unterabschnitt **Cube or Query** können Sie über **[Suche]** (Lupensymbol) nach BEx-Queries oder InfoProviders suchen.
Die Felder *Key Figures*, *Dimensions* und *Properties*, die für die Ausgabe ausgewäht werden können, werden in diesem Unterabschnitt angezeigt. 


#### Preview
Der Unterabschnitt **Preview** zeigt eine Echtzeit-Vorschau der ausgewählten BEx-Query oder des ausgewählten InfoProviders an. Klicken Sie dafür auf die Schaltfläche **[Load Live Preview]**.

#### Schaltflächen
- **[Extraction Settings]** öffnet die [Extraktionseinstellungen](./bw-cube/bw-cube-einstellungen), z.B. **Paketgröße (Package Size)**, **Zeilenbegrenzung (Row Limit)** oder **Automatic Slicing Dimension**. <br>
- **[Load live preview]** lädt eine Echtzeitvorschau einer BEx-Query oder eines InfoProviders ohne eine Extraktion auszuführen.
- **[Show MDX]** zeigt das für die Selektion generierte MDX-Statement, das zur Laufzeit auf dem BW-System ausgeführt wird. Im BICS-Modus ist diese Schaltfläche nicht verfügbar. Um das MDX-Statement zu testen, können Sie die SAP-Transaktion *MDXTEST* verwenden.
- **[Edit Variables]** ermöglicht die Definition von [BEx Query-Variablen](./bw-cube/bw-cube-variablen). 
- **[Edit Runtime Parameters]** ermöglicht die Definition von [Laufzeitparametern](./bw-cube/edit-runtime-parameters). 

Weitere Informationen zum Arbeiten mit der Xtract Cube Komponente finden Sie in den folgenden Unterabschnitten.

---

{% include _content/table-of-contents.html parent=page.childidentifier collection=site.de %}