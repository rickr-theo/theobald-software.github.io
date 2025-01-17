---
ref: yunio-07
layout: page
title: Server Settings
description: Server
product: yunio
parent: yunio
childidentifier: server
permalink: /:collection/:path
weight: 30
lang: de_DE
old_url: /Xtract-Universal-DE/default.aspx?pageid=server
---

Dieser Abschnitt enthält Informationen über die yunIO Server-Einstellungen.
Öffnen Sie die Einstellungen unter dem Menüpunkt **Settings**. 
Speichern Sie Änderungen der Einstellungen mit **[Save]**.

{: .box-note }
**Hinweis:** Starten Sie den yunIO-Server neu, um die Änderungen zu übernehmen.

![Server-Settings](/img/content/yunio/Server-settings.png){:class="img-responsive" }

### Transport Layer Security

Das *Transport Layer Security (TLS)*-Protokoll ermöglicht eine verschlüsselte Datenübertragung.
Wenn TLS aktiviert ist, wird auf den jeweiligen Dienst über eine HTTPS-Verbindung zugegriffen.
Dafür muss ein X.509 Zertifikat installiert sein.
Für mehr Informationen zu TLS, siehe [Microsoft: TLS-Protokoll](https://docs.microsoft.com/de-de/windows/win32/secauthn/transport-layer-security-protocol).

#### Pick Certificate
Klicken Sie auf **[Pick Certificate]** und wählen Sie ein X.509 Zertifikat aus der Liste verfügbarer Zertifikate aus.
Falls das Zertifikat nicht in der Liste oder im Windows Certificate Store aufgelistet ist, installieren Sie das X.509 Zertifikat.

{: .box-note }
**Hinweis:** Je nachdem, ob yunIO auf einer lokalen Serverumgebung oder Cloudumgebung gehostet ist, unterscheidet sich das Vorgehen zur Zertifikaterstellung.
Orientieren Sie sich an den verfügbaren Dokumentationen dazu im Netz oder wenden Sie sich an Ihre Netzwerk-Administratoren.

#### TLS enabled
Wenn ein Zertifikat gewählt wurde, ist die Option **TLS enabled** verfügbar.
Über **TLS enabled** aktivieren oder deaktivieren Sie die Verwendung von Transportverschlüsselung für den Webserver.

### Allowed Origins ([CORS](https://developer.mozilla.org/de/docs/Web/HTTP/CORS))

{: .box-warning }
**Warnung! Cross-Origin Request Blocked** Wenn Sie auf einen CORS-Fehler stoßen, ist die URL Ihres Origins nicht authorisiert auf yunIO zuzugreifen.
Fügen Sie die URL Ihres Origins der Liste authorisierter URL hinzu.

Geben Sie URLs ein, die über Cross-Origin-Requests auf yunIO zugreifen dürfen.
Beispiel: Um einem Tool wie Swagger Inspector zu ermöglichen, Dienste aus yunIO zu laden und zu testen, muss die URL `https://inspector.swagger.io` hinterlegt sein.

{: .box-note }
**Hinweis:** Während der Testphase können Sie ( * ) verwenden, um alle URLs zuzulassen.
Wenn Sie yunIO zum ersten Mal installieren, ist diese Einstellung automatisch gesetzt.

### Services

Definieren Sie hier die Ports für Ihre Service-Aufrufe. Erlaubt sind Ports im Bereich 1-65535. Es ist nicht empfohlen Ports unter 1000 zu verwenden, da diese meist bereits von anderen Diensten besetzt sind und die doppelte Nutzung eines Ports zu Ausfällen und Fehlern führt.

### Services

Define the ports for service consumption here. Valid port numbers range from 1-65535. Although it is not recommended to use ports below 1000 since they often are already taken and using them with different services leads to service disruptions and errors.

#### Default Ports

|Service Name|Http|Https|Description|
|---|---|---|---|
|WebServer|8075|8175|Dieser Port wird vom Webserver verwendet der die Anfragen annimmt, um Services zu starten.|
|WebSockets|8076|8176|Dieser Port wird vom yunIO Designer verwendet, um Konfigurationen, Services und dergleichen anzupassen.|
|Designer|8077|8177|Dieser Port wird genutzt, um den yunIO Designer aufzurufen.|
