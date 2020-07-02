---
ref: xu-microsoft-sql-server-02
layout: page
title: Verbindung
description: Verbindung
product: xtract-universal
parent: microsoft-sql-server
permalink: /:collection/:path
weight: 2
lang: de_DE
old_url: /Xtract-Universal-DE/default.aspx?pageid=sql-server-verbindung
---

Folgende Einstellungen können für die Verbindung zum Microsoft SQL Server definiert werden.

![MSSql-Destination-Details](/img/content/MSSql-Destination-Details.png){:class="img-responsive"}

**Server Name**<br>
Angabe der Host Adresse des SQL Server. Bitte folgende Syntax beachten:

|Syntax | Beispiel |
|:---|:---|
|[ServerName]| `dbtest`|
|[ServerName],[Port]| `dbtest,51433`|
|[ServerName].[Domain],[Port] |  `dbtest.theobald.software,51433`|

Die Angabe des Ports ist nur notwendig, wenn dieser abseits vom SQL Standard editiert wurde.

**Require TLS encryption**<br>
Clientseitiges Erzwingen von [TLS Verschlüsselung](https://docs.microsoft.com/en-us/azure/sql-database/sql-database-connect-query#tls-considerations-for-sql-database-connectivity). Setzt folgende Parameter im Connection String:<br>
* Encrypt = On
* TrustServerCertificate = Off
<br>

siehe auch [Aktivieren von verschlüsselten Verbindungen zur Datenbank-Engine](https://docs.microsoft.com/en-us/sql/database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine?view=sql-server-2017#client-request-encrypt-connect-23h)



**Windows Authentication**<br>
Verwendet den Service Account, unter dem der XU Service läuft, um sich am SQL Server zu authentisieren.

**Impersonate authenticated caller**<br>
Verwendet den Windows AD Benuzer, der die Extraktion ausführt, um sich am SQL Server zu authentisieren [Kerberos Authentisierung.](https://blogs.msdn.microsoft.com/sqlupdates/2014/12/05/sql-server-kerberos-and-spn-quick-reference/)
<br>
Hierfür ist eine ähnliche Konfiguration wie beim [Kerberos Single Sign On](../../fortgeschrittene-techniken/sap-single-sign-on/sso-mit-kerberos-snc) gegen ein SAP System notwendig.

**User Name**<br>
SQL Server Authentisierung - User Name 

**Password**<br>
SQL Server Authentisierung - Passwort

**Database Name**<br>
Name der Datenbank
             
**Test Connection**<br>
Klicken Sie auf die Schaltfläche, um die Datenbankverbindung zu testen. 

**Databankschema** <br>
Standardmäßig wird das Default-Schema dbo des Benutzers verwendet.  <br>
Wenn Sie ein anderes Schema nutzen wollen, dann sollten Sie dieses [Schema als Default](https://docs.microsoft.com/de-de/sql/t-sql/statements/alter-user-transact-sql?view=sql-server-2017) für den Benutzer auf der Datenbank setzen. 
