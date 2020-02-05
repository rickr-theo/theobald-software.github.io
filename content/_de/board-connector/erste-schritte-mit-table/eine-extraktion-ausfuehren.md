---
ref: bc-getting-started-table-03
layout: page
title: Schritt 3 - Eine Extraktion ausführen
description: Schritt 3 - Eine Extraktion ausführen
product: board-connector
parent: erste-schritte-mit-table
permalink: /:collection/:path
weight: 3
lang: de_DE
---

Dieser Schritt ist optional und zeigt, wie Sie sich das Ergebnis der Extraktion im Browser anzeigen lässt, um sicher zu stellen, dass die Extraktion erfolgreich läuft und das gewünschte Ergebnis liefert.  

Um eine angelegte Extraktion auszuführen, markieren Sie die entsprechende Zeile in der Hauptmaske und klicken Sie auf *Run*.

![Extraction-Run](/img/content/Extraction-Run.png){:class="img-responsive"}

Es öffnet sich das nachfolgende Fenster, in dem Sie Details der Ausführung festlegen können.

Die eigentliche Anforderung der Daten erfolgt über eine URL (siehe Screenshot). Es reicht nur die Angabe des Namens, um die Extraktion anzustoßen. Allerdings ist es möglich, über zusätzliche Parameter bestimmte Dinge innerhalb der Extraktion zu übersteuern. Wenn Sie beispielsweise den Defaultwert von 0 (=unbegrenzt) für die maximale Anzahl von Zeilen auf 100 setzen möchten, stellen Sie die *Operationvon Default* auf Override und definieren Sie den gewünschten Parameter in der Value-Spalte. 

![Table-Plants-Run](/img/content/Table-Plants-Run.png){:class="img-responsive"}

Die Parameter *format*, bg und packagesize werden im Abschnitt Settings beschrieben. Um die Extraktion letztendlich auszuführen, klicken Sie auf *Run in Browser*. Ihr Standard-Browser öffnet sich und zeigt das Datenextrakt gemäß den gewünschten Kriterien mit dem gewünschten Format.

![Run-Extraction-Result](/img/content/Run-Extraction-Result.png){:class="img-responsive"}

Bitte beachten Sie, dass die Übergabeparameter (wie rows in unserem Beispiel) nicht zwingend gesetzt sein müssen. Es ist nur dann nötig, sie zu setzen, wenn der in der Extraktion hinterlegte Wert im Nachhinein verändert (bzw. übersteuert) werden soll.


