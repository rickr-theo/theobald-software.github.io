---
ref: ecscore-nintex-workflow-cloud-nwc-04
layout: page
title: Verbindung anlegen
description: Verbindung anlegen
product: ecs-core
parent: nintex_workflow_cloud
permalink: /:collection/:path
weight: 4
lang: de_DE
old_url: /ECS-Core-DE/default.aspx?pageid=verbindung_anlegen
---

Nach erfolgreichem Importieren der OpenAPI Definition und Veröffentlichung des benutzerdefinierten Konnektors können Sie eine neue Verbindung in der Nintex Workflow Cloud anlegen. Diese Verbindung zeigt auf die in ECS Core angelegten SAP Services und ermöglicht die Verbindung zum SAP System.    

Das vorliegende Beispiel ist erläutert mit einem API Key als Authentifizierungsmethode. Bitte verwenden Sie die Einstellungen für Authentifizierung per API Key im Connection Dialog des Webservice Designers. API Key wird dann automatisch auch als Authentifizierungsmethode vorgeschlagen, wenn Sie eine neue Verbindung anlegen.  

Klicken Sie auf *Connections* und *Add new*, um eine neue Verbindung anzulegen und wählen Sie den vorab erstellten benutzerdefinierten Konnektor aus der Liste aus:

![ecscore-nwc_8](/img/content/ecscore-nwc_8.png){:class="img-responsive"}

Geben Sie der Verbindung einen Namen und fügen Sie einen gültigen API Key in folgender Form ein:
APIKEY [ECS Core API Key]

Beispiel: APIKEY QjGCMTMxMjE0MTA3NDhCMUE5MUNZTzAyQjBDRTg1OUP= (vgl. Verbindungseinstellungen mit API Key in [Webservice Authentifizierung](../../webservices/webservice_authentifizierung))

![ecscore-nwc_9](/img/content/ecscore-nwc_9.png){:class="img-responsive"}

Die Verbindung kann anschließend in einem Nintex Workflow Cloud Workflow genutzt werden.