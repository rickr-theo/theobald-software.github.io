---
ref: xi-sap-connection-01
layout: page
title: Der Connection Manager
description: Der Connection Manager
product: xtract-is
parent: sap-verbindung
permalink: /:collection/:path
weight: 1
lang: de_DE
---

Jede Xtract IS Datenquelle benötigt einen Xtract IS Connection Manager, um über ihn auf das SAP-System zuzugreifen. Um innerhalb eines SSIS Packages einen neuen Connection Manager anzulegen, klicken Sie mit der rechten Maustaste unten in den Bereich für die Connection Manager und wählen Sie *Neue Verbindung*. <br>
Wählen Sie den Connection Manager XTRACT (siehe Bild).

![Connection-Manager-01](/img/content/Connection-Manager-01.png){:class="img-responsive"}

Um den Connection Manager korrekt zu konfigurieren, klicken Sie doppelt auf das Verbindungsmanager-Symbol für die Xtract-Verbindung.

![Connection-Manager-02](/img/content/Connection-Manager-02.png){:class="img-responsive"}

Die folgende Maske öffnet sich. Sie müssen nun die Anmeldedaten (*Benutzername, Mandant, Passwort, Sprache*) und die Angaben zum Zielsystem ausfüllen. 

![Connection-Manager](/img/content/Connection-Manager.png){:class="img-responsive"}

**Zielsystem**

Das SAP-Zielsystem, welches ein Application-Server oder ein Message-Server (Load Balancing) sein kann.

Im Fall eines Applikationsservers werden folgende Angaben benötigt: 

- Name oder IP-Adresse des Applikationsservers (Eigenschaft Host) 
- Systemnummer, eine Zahl zwischen 0 und 99 (Eigenschaft SystemNumber)

Im Fall einer Anmeldung an einem Message Server (Load Balancing) sind folgende Daten zu füllen: 

- Dreistellige System-ID (Eigenschaft SID, z.B. MSS) 
- Name oder IP-Adresse des Message-Servers (Eigenschaft MessageServer) 
- Logon-Gruppe (Eigenschaft LogonGroup, i.d.R. ist das PUBLIC)

SAP Dokumentation: [Load Balancing](https://help.sap.com/saphelp_dm40/helpdata/de/22/04295c488911d189490000e829fbbd/content.htm?no_cache=true) <br>

**SAP-Router**

Falls Sie auf das SAP-System (Application-Server oder Message-Server) über einen SAP-Router zugreifen, setzen Sie den Routerstring unmittelbar vor dem Hostnamen bzw. dem Message-Server. <br>
Beispiel: Wenn der Anwendungsserver "hamlet" ist und der Router-String "/H/lear.theobald-software.com/H/" lautet, sollten Sie die Host property auf "/H/lear.theobald-software.com/H/hamlet" setzen.

SAP Dokumentation: [SAP-Router](https://help.sap.com/saphelp_nw70/helpdata/de/4f/992df1446d11d189700000e8322d00/content.htm?no_cache=true) <br>

Falls Sie nicht wissen, welche Parameter Sie eingeben müssen, können Sie die Informationen im SAP Logon Pad in den *Properties* nachschauen.
Fragen Sie ansonsten bei Ihrer SAP-Basis nach. 

Wenn alles korrekt ausgefüllt ist, klicken Sie auf *Test Connection*, um zu prüfen, ob das SAP-System erreichbar ist. 

**Trace Directory**<br>
Sie haben die Möglichkeit Debug-Informationen zu loggen. Wenn Sie Debug-Informationen loggen wollen, so muss im Connection Manager in das Feld [*Trace Directory*](https://kb.theobald-software.com/general/how-to-activate-tracing-for-xtract-products?fromSearch=true) ein gültiger Pfad eintragen werden. <br> 

Bitte beachten Sie, dass das Logging in der Regel nur nach Aufforderung durch den Support aktiviert werden sollte. Beim Logging werden eine Vielzahl von Informationen gesammelt. Dies kann bei permanent aktiviertem Logging dazu führen, dass die Kapazitätsgrenzen des Speichermediums schnell erschöpft ist. Das Standard Logging ist von dieser Einstellung unabhängig und wird auch bei einem leeren Trace Directory Eintrag ausgeführt.

**RFC Bibliothek (API)**: Klassisch oder NetWeaver. <br>

Die RFC API (Remote Function Call) erlaubt den Aufbau einer RFC-Verbindung zu einem SAP-System von einem externen System, welches als Client oder Server mit dem SAP-System kommunizieren kann. <br>
Die RFC API existiert in zwei unterschiedlichen Versionen: 
- Klassische RFC Bibliothek (librfc32.dll).
- NetWeaver RFC Bibliothek (sapnwrfc.dll). 

Hinweis: Wenn Sie die NetWeaver RFC-Bibliothek bei DeltaQ oder OHS-Extraktionen nutzen, muss die RFC-Destination in der SM59 auf Unicode eingestellt sein.

Weitere Informationen finden Sie hier [RFC API: Classical & SAP NetWeaver](https://help.sap.com/doc/saphelp_nw73ehp1/7.31.19/en-US/48/a994a77e28674be10000000a421937/frameset.htm) in der SAP Dokumentation. 
<br>
SAP hat den [Support für die librfc32.dll](https://blogs.sap.com/2012/08/15/support-for-classic-rfc-library-ends-march-2016/) eingestellt. Diese funktioniert nach unserer Erfahrung jedoch nach wie vor und läuft in machen Fällen (z.B. DeltaQ) stabiler als die NetWeaver RFC Bibliothek.

**Additions**

![XIS_ConnectionManager_AdditionsTab](/img/content/XIS_ConnectionManager_AdditionsTab.png){:class="img-responsive" width="600px" }

**SNC enabled**

Siehe auch [SAP-Verbindung mit SNC](./sap-verbindung-mit-snc). <br>
Aktivieren Sie [SNC](https://help.sap.com/viewer/e73bba71770e4c0ca5fb2a3c17e8e229/7.5.8/en-US/e656f466e99a11d1a5b00000e835363f.html) (Secure Network Connection) für die Datenverschlüsselung zwischen SAP und Xtract IS.<br>
Erfordert auch auf SAP-Seite entsprechende Einstellungen. Bitte wenden Sie sich zur Unterstützung an Ihr SAP-Basis-Team.

**SNC Library (32 Bit, Visual Studio)**

Pfad zur 32-Bit-Version der verwendeten Verschlüsselungsbibliothek (beim Ausführen des Pakets im Debug-Modus in VS/SSDT).

**SNC Library (64 Bit)**

Pfad zur 64-Bit-Version der verwendeten Verschlüsselungsbibliothek (bei Ausführung des bereitgestellten Pakets auf dem SSIS-Server).

**Partner Name**

SNC-Partnername

**Quality of Protection**

Definiert die SNC-Schutzstufe.

**Expert Options**

Seit 09/2017 werden SAP-Verbindungsparameter nicht mehr als einzelne *Connection Strings*, sondern als *Properties* gespeichert.
Für jede Komponente des *Connection Strings* existiert eine *Property* (siehe Screenshot unten).

Dies ermöglicht die Verwendung einer [sensitiven Umgebungsvariablen](./sensitive-umgebungsvariablen-in-ssis) für das Passwort im Katalog der Integration Services.<br>
Der *Connection String* (siehe *Legacy storage mode* unten) unterstützte keine sensitiven Umgebungsvariablen.
Dies bietet eine stärkere Verschlüsselung als die Passwort-Verschleierung (siehe unten).

Sie können entweder *Connection Properties* oder einen *Connection String* verwenden, nicht beides.

**Legacy storage mode (connection string)**

Die SAP-Verbindungsparameter werden über einen einzigen *Connection String* eingestellt (Standard in XIS-Versionen vor 09/2017).

**Obfuscate Password**

Das SAP-Verbindungspasswort wird verschleiert, so dass es nicht im Klartext gespeichert wird. Wird standardmäßig eingeschaltet, wenn der *Legacy storage mode* aktiviert wird.

![XIS_Connection_Properties](/img/content/XIS_Connection_Properties.png){:class="img-responsive" width="600px". }