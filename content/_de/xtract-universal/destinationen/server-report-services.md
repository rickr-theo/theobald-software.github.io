---
ref: destinations-108
layout: page
title: SQL Server Reporting Services
description: SQL Server Reporting Services (SSRS)
product: xtract-universal
parent: destinationen
childidentifier: ssrs
permalink: /:collection/:path
weight: 108
lang: de_DE
progressstate: 5
---

Der folgende Abschnitt behandelt die Verwendung von Xtract Universal für eine SAP Integration in SSRS.

## Voraussetzung


Um sie SSRS-Destination zu nutzen, benötigen Sie folgende Komponenten:

- Visual Studio 2017 oder höher
- das [Microsoft Reporting Services Projects](https://marketplace.visualstudio.com/items?itemName=ProBITools.MicrosoftReportProjectsforVisualStudio) Plugin (Version 2.6.11 oder höher) für Visual Studio.
- Power BI Report Server (Januar 2020 oder später)
- Xtract Universal (Version 4.29 oder höher)

{: .box-note }
**Hinweis:** Der Power BI Report Builder wird nicht unterstützt.


## Installation

Um die SSRS-Destination zu nutzen, installieren Sie das [Microsoft Reporting Services Projects](https://marketplace.visualstudio.com/items?itemName=ProBITools.MicrosoftReportProjectsforVisualStudio) Plugin in Visual Studio.
Nach der Installation, schließen Sie Visual Studio.

Microsoft SQL Server Reporting Services unterstützt eine große Auswahl von Datenquellen out-of-the-box. 
Um Xtract Universal als Datenquelle hinzuzufügen, installieren Sie die [Xtract Universal Data Extension](#installation-der-xtract-universal-data-extension) für Visual Studio **und** den Report Server.
Die Erweiterung muss auf beiden Umgebungen installiert sein, um die von Xtract Universal extrahierten Daten zu konsumieren, siehe folgende Grafik:

![XU-Setup](/img/content/xu/ssrs/XUDataExtensionInstallation.png){:class="img-responsive" width="600px" }

Die Erweiterung wird bei der Installation des [Xtract Universal Setup](../einfuehrung/installation-und-update) automatisch installiert.
Um die Installation zu beenden, schließen Sie Visual Studio.

{: .box-note }
**Hinweis:** Achten Sie darauf, dass Sie immer die aktuelle Version des *Microsoft Reporting Services Projects* Plugins und von Xtract Universal installieren.


Nach der Installation der `C:\Program Files\XtractUniversal\ssrs\SSRSDataExtensionSetup.exe` erstellt das Setup die folgenden Einträge und Erweiterungen im Installationsverzeichnis von Visual Studio:
- `C:\Program Files (x86)\Microsoft Visual Studio\2019\Enterprise\Common7\IDE\CommonExtensions\Microsoft\SSRS\XUDataExtension2020.05.dll`
- `C:\Program Files (x86)\Microsoft Visual Studio\2019\Enterprise\Common7\IDE\CommonExtensions\Microsoft\SSRS\Theobald.Common.dll`
- `C:\Program Files (x86)\Microsoft Visual Studio\2019\Enterprise\Common7\IDE\CommonExtensions\Microsoft\SSRS\Theobald.Distillery.Common.dll`
- `C:\Program Files (x86)\Microsoft Visual Studio\2019\Enterprise\Common7\IDE\CommonExtensions\Microsoft\SSRS\Theobald.Net.dll`
- `C:\Program Files (x86)\Microsoft Visual Studio\2019\Enterprise\Common7\IDE\CommonExtensions\Microsoft\SSRS\RSReportDesigner.config`

### Installation der Xtract Universal Data Extension

Um die Xtract Universal Erweiterung auf mehreren Umgebungen zu installieren, ohne den kompletten Xtract Universal Designer zu installieren, führen Sie folgende Schritte aus:

1. Stellen Sie sicher, dass das *Microsoft Reporting Services Projects* Plugin für Visual Studio bereits installiert und aktiviert ist. 
2. Schließen Sie Visual Studio.
3. [Installieren Sie Xtract Universal](../einfuehrung/installation-und-update) auf der Umgebung, auf der die Lizenz läuft.
4. Nach der Installation, öffnen Sie das Verzeichnis von Xtract Universal, z.B. `C:\Program files\Xtract Universal\` und kopieren Sie den Ordner `\ssrs` auf jede Umgebung, auf der Visual Studio verwendet wird um Reports zu erstellen oder auf denen der Report Server läuft.
5. Führen Sie die *SSRSDataExtensionSetup.exe* als Administrator aus, um die Xtract Universal Erweiterung auf allen kompatiblen Versionen von Visual Studio und/oder dem Report Server zu installieren. 
6. Nach der Installation auf dem Report Server starten Sie den Report Server neu, damit die Änderungen in Kraft treten.
Sie können den Server im *Configuration Manager* neu starten. Klicken Sie auf **[stop]** und anschließend auf **[start]**.

Um die Erweiterung zu deinstallieren, verwenden Sie die *uninstall.bat* Datei aus dem `\ssrs`-Ordner des Xtract Universal Verzeichnisses.

{: .box-note }
**Hinweis:** Wenn das *Reporting Services Projects* Plugin in Visual Studio upgedatet wird, ist die Xtract Universal Data Extension nicht mehr verfügbar. Die Xtract Universal Data Extension muss dann neu installiert werden.

Sollten bei der Installation der Xtract Universal Data Extension Schwierigkeiten auftreten, Senden Sie die Log-Datei aus dem Verzeichnis `C:\Program Files\XtractUniversal\ssrs\log.txt` an [Theobald Support](mailto:support@theobald-software.com).


## Verbindung

{% include _content/de/xu-specific/destinationen/general/connection.md %}	 

### Destination Details

Für das Anlegen einer SSRS Zielumgebung müssen keine weiteren Einstellungen vorgenommen werden.

![ssrs-create-destination](/img/content/ssrs-create-destination.png){:class="img-responsive"}

## Einstellungen

### Destination Settings öffnen

1. Eine bestehende Extraktion anlegen oder auswählen (siehe auch [Erste Schritte mit Xtract Universal](../erste-schritte/eine-neue-extraktion-anlegen)).
2. Klicken Sie auf **[Destinations]**. Das Fenster "Destination Settings" wird geöffnet.
![Destination-settings](/img/content/xu/xu_designer_destination.png){:class="img-responsive"}

Die folgenden Einstellungen können für die Destination definiert werden. 
  
### Destination Settings - Destinationseinstellungen

![ssrs-configuration](/img/content/ssrs-configuration.png){:class="img-responsive"}

{% include _content/de/xu-specific/destinationen/general/column-name-style.md %}

{% include _content/de/xu-specific/destinationen/general/date-conversion.md %}

## SSRS in Visual Studio


Der folgende Abschnitt zeigt, wie man in der SQL Server Reporting Services (SSRS) Umgebung über Xtract Universal auf SAP-Daten zugreift.

### SAP-Daten im Xtract Universal Designer extrahieren

Um SAP-Daten in der SQL Server Report Server (SSRS) Umgebung zur Verfügung zu stellen, wird im ersten Schritt eine entsprechende Extraktion im Xtract Universal Designer erstellt.

Informationen bzgl. der Erstellung von Extraktionen finden Sie unter [Erste Schritte](../erste-schritte).<br>
Verwenden Sie für die Extraktion die [*SQL Server Reporting Service* Destination](#verbindung).


### Eine Extraktion als Datenquelle in Visual Studio hinzufügen

Die folgenden Schritte beschreiben, wie man eine Xtract Universal Datenquelle in Visual Studio hinzufügt:

1. Erstellen Sie ein neues "Report Server Project" in Visual Studio. <br>
![New-Project](/img/content/xu/ssrs/New-Project.png){:class="img-responsive"}
2. Rechtsklicken Sie auf den Ordner *Shared Data Sources* im *Solution Explorer* und wählen Sie **Add New Data Source**. Das Fenster "Shared Data Source Properties" öffnet sich.
3. Weisen Sie im Tab *General* der neuen Datenquelle einen Namen zu oder verwenden Sie den Standardnamen (1).
4. Wählen Sie den Typ *Xtract Universal* aus der Drop-Down-Liste aus (2). <br>
Falls *Xtract Universal* nicht verfügbar oder in Großbuchstaben ist, prüfen Sie ob die aktuelle Xtract Universal Version und das aktuelle *Microsoft Reporting Services Projects* Plugin installiert sind.
5. Geben Sie einen *connection string* (3) zum Xtract Universal [Web-Server](../sicherheit/serversicherheit) im Format `Url=http://[host]:[port]/` ein, z.B. `Url=http://localhost:8065/`. Beachten Sie die Groß-Kleinschreibung.
![Shared-Data-Source-Properties](/img/content/xu/ssrs/Shared-Data-Source-Properties.png){:class="img-responsive"}
6. Optional (nur nötig, wenn die [XU-Serversicherheit](../sicherheit/serversicherheit) konfiguriert wurde oder an das SAP-Quellsystem entsprechende Credentials übergeben werden müssen): Wechseln Sie in den *Credentials* Tab (4) und geben Sie Ihren [Benutzernamen und Passwort](../sicherheit/benutzerverwaltung) für Xtract Universal ein.
7. Bestätigen Sie Ihre Eingabe mit **[OK]**.

Wenn *Xtract Universal* trotz aktuellem *Microsoft Reporting Services Projects* Plugin und aktuellem Xtract Universal nicht in der Drop-Down-Liste (2) verfügbar ist, schicken Sie die Log-Datei aus `C:\Program Files\XtractUniversal\ssrs\log.txt` an den [Theobald Support](mailto:support@theobald-software.com).

{: .box-tip }
**Tipp:** Der *connection string* ist im URL string aus dem "Run Extraction"-Fenster des Designers enthalten. Kopieren Sie den String bis zum '?' und fügen Sie ihn als *connection string* in Visual Studio ein.

{: .box-note }
**Hinweis:** Wenn in den [XU Webserer Einstellungen](../sicherheit/serversicherheit) **https Restricted...** oder **https Unrestricted** aktiviert ist, muss auf dem Rechner auf dem der SSRS Server läuft die Registry entsprechend der [Microsoft Hilfe (Konfigurieren für starke Kryptografie)](https://docs.microsoft.com/de-de/mem/configmgr/core/plan-design/security/enable-tls-1-2-client#configure-for-strong-cryptography) angepasst werden.

### Einen Report mit einer Xtract Universal Datenquelle erstellen

Die folgenden Schritte beschreiben, wie man in Visual Studio einen Report mit einer Xtract Universal Datenquelle erstellt:

1. [Fügen Sie eine Extraktion als Datenquelle in Visual Studio hinzu](#eine-extraktion-als-datenquelle-in-visual-studio-hinzufügen).
2. Rechtsklicken Sie auf den Ordner *Reports* im *Solution Explorer* und wählen Sie **Add New Report**. Das Fenster "Report Wizard" öffnet sich.
3. Wählen Sie im Assistenten eine Datenquelle und klicken Sie auf **[Next]**.
4. Klicken Sie auf **[Query Builder...]**. Das Fenster "Query Designer" öffnet sich.
5. Wählen Sie eine Xtract Universal Extraktion aus dem Drop-Down-Menü aus (5). <br>
Wenn keine Extraktionen angezeigt werden, prüfen Sie den *connection string* (3) in der Datenquelle und prüfen Sie, ob in Xtract Universal eine Extraktion mit einer *SQL Server Reporting Services* Destination existiert.
Wenn Ihnen der unten abgebildete Editor nicht angezeigt wird, klicken Sie auf **Edit as Text**.
![Query-Designer](/img/content/xu/ssrs/Query-Designer.png){:class="img-responsive"}
6. Optional: Bearbeiten Sie die [Laufzeitparameter](../extraktionen-ausfuehren-und-einplanen/extraktionsparameter) der Extraktion (6). 
Parameteränderungen werden im Query string angezeigt (7). Ungültige Eingaben werden rot markiert. Eine Fehlermeldung erhalten Sie, wenn Sie den Mauszeiger auf die Markierung bewegen.
7. Klicken Sie auf **[Preview]** (8) um die Extraktion im *Preview Mode* auszuführen. 
8. Bestätigen Sie Ihre Eingabe mit **[OK]**. Der Query Builder schließt sich. 
9. Prüfen Sie, dass der Query string aus dem Query Builder im Report-Assistenten angezeigt wird, bevor Sie auf **[Next]** klicken.
![Report-Wizard](/img/content/xu/ssrs/Report-Wizard.png){:class="img-responsive"}
10. Richten Sie den Report entsprechend Ihrer Anwendung ein und beenden Sie den Report-Assistenten.

Nachdem der Report erstellt wurde, können Sie auf den Query Builder zugreifen, indem Sie unter *Report Data* über Rechtsklick auf *Dataset* **Query...** auswählen. 

{: .box-tip }
**Tipp:** Das Durchreichen des (Windows) Users, der den Bericht auf dem Report Server oder bei der Entwicklung in Visual Studio ausführt, wird unterstützt. 
Single Sign On in SAP ist über diesen Weg ebenfalls möglich.
Voraussetzung hierfür ist die Einrichtung der [Web Server Authentifizierung](../server/server_einstellungen#web-server) in Xtract Universal bzw. die Einrichtung des [Single Sign On](../fortgeschrittene-techniken/sap-single-sign-on).

### Parametrisierung

Der Xtract Universal Designer verwendet für die Parametrisierung [Laufzeitparameter](../extraktionen-ausfuehren-und-einplanen/extraktionsparameter).

Die Laufzeitparameter sind im Query Builder verfügbar. Sie können eine der folgenden Eigenschaften (**Behaviours**) annehmen: <br>

- *Default:* Verwendet den Wert, der im Xtract Universal Designer definiert wurde.
- *Constant:* Geben Sie hier einen konstanten Wert ein für den Parameter ein.
- *Parameterized:* Geben Sie hier den Namen eines dynamischen Abfrageparameters ein, der zu Laufzeit übergeben wird.
Der Parameter unterstützt die Verwendung von Formeln.

 {: .box-note }
**Hinweis:** Laufzeitparameter erlauben die Eingabe eines einzelnen Parameters.  
Wenn man mehrere Abfrageparameter verwenden möchte, kann man mit den Bordmitteln des VS Report Designers einen *berechneten Abfrageparameter* zusammenbauen und diesen als Laufzeitparameter übergeben, siehe [Using Computed Query Parameters for SSRS with Xtract Universal](https://kb.theobald-software.com/xtract-universal/xu-ssrs-parameterizing-in-vs).

#### Dynamische Laufzeitparameter definieren

Verwenden Sie VS Abfrageparameter als Eingabe für Xtract Laufzeitparameter.

1. Um einen neuen Abfrageparameter zu erstellen, rechtklicken Sie auf das Dataset im Fenster *Report Data* und wählen Sie **Dataset Properties** Das Fenster "Dataset Properties" öffnet sich.
2. Wechseln Sie in den Tab *Parameters* und klicken Sie auf **[Add]**.
![Query-Parameter](/img/content/xu/ssrs/query-parameters.png){:class="img-responsive"}
3. Geben Sie einen *Parameter Name*(1) und einen *Parameter Value* ein oder verwenden Sie **[f(x)]**, um Formeln hinzuzufügen oder mehrere Eingaben zu kombinieren.
4. Wechseln Sie in den Tab *Query* und klicken Sie auf **[Query Designer...]**. Das Fenster "Query Designer" öffnet sich.
![Query-Designer](/img/content/xu/ssrs/QueryDesigner.png){:class="img-responsive"}
5. Wählen Sie *Parameterized* als **Behaviour** des Laufzeitparameters aus, den Sie dynamisieren möchten.
6. Geben Sie den Namen des Abfrageparameters (1) unter **Value** ein.
7. Bestätigen Sie Ihre Eingabe mit **[OK]**.


#### Optionale Parameter

Wenn ein Abfrageparameter NULL ist, wird der Parameter zu Laufzeit nicht übergeben und der Parameter wird ignoriert.

 {: .box-note }
**Hinweis:** Abhängig vom Extraktionstyp können einige Laufzeitparameter nicht ignoriert werden. Insbesondere *Custom Parameters* sind i.d.R. verpflichtend.

1. Rechtsklicken Sie auf das Eingabefeld, das optional sein soll und wählen Sie *Parameter Properties*. Das Fenster "Report Parameter Properties" öffnet sich.
![Input-Field](/img/content/xu/ssrs/optional-params.png){:class="img-responsive"}
2. Aktivieren Sie die Checkbox **Allow null value** im Tab *General*.
3. Bestätigen Sie Ihre Eingabe mit **[OK]**. Eine Checkbox **NULL** wird neben Ihrem Eingabefeld angezeigt.
4. Wenn die Checkbox **NULL** aktiv ist, wird der Parameter zur Laufzeit ignoriert.

 {: .box-tip }
**Tipp:** Sie können auch einen berechneten Abfrageparameter verwenden, um den Wert NULL zu erhalten. Erstellen Sie eine Formel, die *Nothing* als Wert zurückgibt.

******
## Weiterführende Links
- [Berichtsentwurfstipps (Berichts-Generator und SSRS)](https://docs.microsoft.com/de-de/sql/reporting-services/report-design/report-design-tips-report-builder-and-ssrs?view=sql-server-ver15)
- [Reporting Services-Tutorials (SSRS)](https://docs.microsoft.com/de-de/sql/reporting-services/reporting-services-tutorials-ssrs?view=sql-server-ver15)
- [Hinzufügen eines Abfrageparameters zum Erstellen eines Berichtsparameters](https://docs.microsoft.com/de-de/sql/reporting-services/tutorial-add-a-parameter-to-your-report-report-builder?view=sql-server-ver15#Query)
- [Using Computed Query Parameters for SSRS with Xtract Universal](https://kb.theobald-software.com/xtract-universal/xu-ssrs-parameterizing-in-vs)