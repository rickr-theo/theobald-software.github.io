---
ref: xi-requirements-and-installation-04
layout: page
title: Lizensierung
description: Über Lizensierung von Xtract IS
product: xtract-is
parent: voraussetzungen-und-installation
permalink: /:collection/:path
weight: 4
lang: de_DE
old_url: /Xtract-IS-DE/default.aspx?pageid=lizenz-einspielen
---
### Über das Lizenzkonzept von Xtract IS
Die folgende Grafik zeigt, auf welchen Rechnern die Installation von Xtract IS mit einer gültigen Lizenz erforderlich ist. <br>
![client_Server_architecture_xis_final](/img/content/xis/client_server_xis.png){:class="img-responsive" width="800px"} <br>

Die Lizenzierung von Xtract IS erfolgt pro Windows-Server auf dem SSIS-Pakete bereitgestellt und ausgeführt werden. Dieselbe Lizenzdatei kann auf den lokalen Rechnern für die Entwicklung der SSIS-Pakete verwendet werden.
Mit der Installation von Xtract IS wird automatisch eine Demo-Lizenz installiert. <br>
Die Produktlizenz ist an Ihr Unternehmen und einen bestimmten Servernamen gebunden.

### Installation der Xtract IS-Lizenz - XtractISLicense.json
1. Um die reguläre Lizenz zu installieren, wählen Sie die ausführbare Xtract IS Lizensmanager-Datei im Installationsverzeichnis von Xtract IS aus:<br>
`C:\Program Files\XtractIS\XtractLicenseManager.exe`
Der Lizenzmanager wird geöffnet.<br>
![XIS_License_Manager](/img/content/xis/xis_license-manager.png){:class="img-responsive" width="400px"}
2. Klicken Sie auf **[Install]**. Das Fenster "Install Xtract License" wird geöffnet.
3. Suchen Sie die reguläre Datei "XtractISLicense.json" im Installationsverzeichnis von Xtract IS:
`C:\Program Files\XtractIS\XtractISLicense.json`
4. Schließen und starten Sie den Lizenzmanager neu, um die korrekt installierte Lizenz anzuzeigen. <br>
![XIS_Lizenz_Info](/img/content/XIS_License_Info.png){:class="img-responsive" width="400px"}

<div class="alert alert-success">
  <i class="fas fa-lightbulb"></i> <strong>Tipp:</strong> Um Ihre aktuellen Lizenzdaten einzusehen, klicken Sie auf den Info-Link, der sich oben in jedem Komponenten-Editor befindet.<br>
</div>


### Aktualisierung der Xtract.License.dll auf XtractISLicense.json
Die ältere Version der Xtract IS Lizenzdatei ist eine .dll-Datei, die im GAC registriert wurde.
In den neueren Versionen von Xtract IS wird die Lizenzdatei in Form einer .json-Datei zur Verfügung gestellt.<br>
Kopieren Sie die XtractISLicense.json in einen der folgenden Pfade:<br>
`CSIDL_COMMON_APPDATA\TheobaldSoftware\XtractIS\` <br>
 oder `C:\ProgramData\TheobaldSoftware\XtractIS\`

Wenn Sie eine ältere .dll-Lizenzdatei haben, muss die ältere Version entfernt werden, um die neuere Version nutzen zu können.

Um die neuere Version der Lizenz nutzen zu können, muss die ältere Version entfernt werden.

#### Entfernen der älteren Xtract.License.dll aus dem GAC
1. Führen Sie die Windows-Kommandozeile als Administrator aus.
2. Führen Sie die Deinstallationslizenzdatei aus: `C:\Program Files\XtractIS>UninstallDllLicense.bat` <br>
Die .dll-Lizenz wird entfernt.
3. Führen Sie die Installation der neueren XtractISLicense.json-Datei durch.
