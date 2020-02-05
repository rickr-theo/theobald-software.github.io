Um die Server-Einstellungen zu ändern, klicken Sie im Hauptmenü auf *Server -> Settings*. 

Die Server-Einstellungen verteilen sich auf zwei Reiter: *Configuration Server* und *Web Server*.

### Configuration Server

![XU3_ServerSettings_config_tab](/img/content/XU3_ServerSettings_config_tab.png){:class="img-responsive"}

**Port**<br>
Definiert die Portnummer, über die der Server mit dem Designer kommuniziert. Standardport ist 8064. Wird ein anderer Port verwendet, muss dieser in der Anmeldemaske dem Hostnamen mit :[Port] hinten angestellt werden.

**Max. age of log files (days)**<br>
Definiert das maximale Alter der Logdateien des Config-Servers in Tagen. Danach werden die Logdateien gelöscht. 

**Authentication methods**<br>
siehe Kapitel [Benutzerverwaltung](../sicherheit/benutzerverwaltung)

**Select X.509 certificate**<br>

Siehe Kapitel [X.509 Zertifikat installieren](../sicherheit/x.509-zertifikat-installieren)

**Access Management**<br>
siehe Kapitel [Zugriffsverwaltung](../sicherheit/zugriffsverwaltung)

### Web Server

![XU3_ServerSettings_web_tab](/img/content/XU3_ServerSettings_web_tab.png){:class="img-responsive"}

**Protocol/Access control**

**HTTP - Unrestricted / HTTP port**<br>
Definiert die Portnummer, über die der Server den Aufruf der Extraktionen über HTTP entgegen nimmt. 

**HTTPS - Unrestricted / HTTPS port**<br>
Aktiviert den sicheren Datentransfer via HTTPS. Der run-Befehl generiert eine HTTPS-URL. Definiert den HTTPS Listener Port.

Wenn Sie Daten über HTTPS empfangen wollen, müssen Sie ein TLS-Zertifikat installieren, damit der Server den HTTPS-Port verwalten kann. 
Siehe Kapitel [X.509 Zertifikat installieren](../sicherheit/x.509-zertifikat-installieren)

**HTTPS - Restricted to AD users with Designer read access**<br>
Siehe *HTTPS - Unrestricted*. Darüber hinaus ermöglicht diese Einstellung eine Zugriffskontrolle auf die Ausführung von Extraktionen. Extraktionen können nur von Windows AD Benutzern ausgeführt werden, denen im Tabreiter *Configuration Server* mindestens *Read Access* zugewiesen wurde. Siehe auch [Release Note](https://kb.theobald-software.com/release-notes/XtractUniversal-3.11.0.html) und Kapitel [Serversicherheit](../sicherheit/serversicherheit).

**Misc.**

**Max. age of log files (days)**<br>
Definiert das maximale Alter der Webserver-Logdateien in Tagen. Danach werden die Logdateien gelöscht. 

**Enable setup distribution for clients**<br>
Legt fest, ob das Setup der XU-Version, die auf dem Server läuft, vom Server heruntergeladen werden kann.<br>
Wenn man sich mit einer älteren Designer-Version an einem neueren Server anmeldet und diese Option aktiviert ist,
fragt der Designer, ob man das neuere Setup herunterladen möchte.

**Result cache**

**Target directory**<br>
Definiert das Verzeichnis, in dem Extraktionen gepuffert werden. Default ist der Ordner result-cache im Installationsverszeichnis von Xtract Universal.

**Max. cached runs**<br>
Definiert die maximale Anzahl der Ergebnisse verschiedener Extraktionen im Puffer.

**Max. age (minutes)**<br>
Definiert das maximale Alter in Minuten einer Extraktion im Puffer.

