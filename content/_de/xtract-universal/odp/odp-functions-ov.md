---
ref: xu-odp-introduction
layout: page
title: Funktionsübersicht
description: Funktionsübersicht
product: xtract-universal
parent: Operational Data Provisioning (ODP)
permalink: /:collection/:path
weight: 1
lang: de_DE
progressstate: 5
---

Der folgende Abschnitt beschreibt die Einstellungen der Komponente Xtract ODP. Die Einstellungen können im Hauptfenster “ODP” der Komponente angepasst werden. 
![ODP Component](/img/content/odp/odp_overview.png){:class="img-responsive"}

###  Funktionsübersicht

Das Fenster "ODP" besteht aus folgenden Unterabschnitten:
- [Operational Data Provider](./odp-define#ein-objekt-data-object-suchen) (1) - Suche und Anzeige des Namens des Quellobjekts.
- Additional info (2) - Zeigt den ODP-Provider-Kontext und den Datentyp des Quellobjekts an.
- [Update mode](./odp-functions-ov#load-verfahren-update-mode) (3) - Definiert das Load-Verfahren - Full-Load oder Deltaverarbeitung.
- [Fields](./odp-functions-ov#selektion-und-filter) (4) - Ermöglicht die Auswahl und Einstellung der Filteroptionen für [Extraktoren](./odp-extractors).
- Preview (5) - Klicken Sie auf **[Load Live Preview]**, um eine Echtzeit-Vorschau der Extraktionsdaten anzuzeigen.

#### Schaltflächen
- **[General Settings](../erste-schritte/allgemeine-einstellungen)** - Die *General Settings* beinhalten Einstellungen zu Sicherheit, Verschlüsselung und Schlüsselwörtern.
- **[Show active subscriptions ](./odp-settings#abonnements)** - Schaltfläche zum Anzeigen der Details zum Abonnentenprozess.
- **[Edit runtime parameters](./odp-settings#parameter-bearbeiten)** - Schaltfläche zum Definieren der [Laufzeitparameter](../extraktionen-ausfuehren-und-einplanen/extraktionsparameter), die als Platzhalter zum Auswählen der Daten verwendet werden können.
- **[Advanced Settings](./odp-settings#fortgeschrittene-einstellungen)** - Enthält Einstellungen für die **package size** der Extrraktion..
- **[Load Live Preview]** - Schaltfläche zum Anzeigen der Echtzeitvorschau der zu extrahierten Daten ohne Ausführung einer Extraktion. 

{% include _content/de/odp/odp-settings-update_mode.md %} 
{% include _content/de/odp/odp-settings-filtering.md %}
