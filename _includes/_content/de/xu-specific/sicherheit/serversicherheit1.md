

### Voraussetzungen: Aktivierung der TLS Verschlüsselung

Bei beiden Typen der Zugriffsbeschränkung wird auf den Webserver über eine https-Verbindung zugegriffen. Dafür muss das X.509 Zertifikat installiert sein.
Falls das Zertifikat nicht im Windows Certificate Store aufgelistet ist, [installieren Sie das X.509 Zertifikat](./x.509-zertifikat-installieren#x509-zertifikat-erstellen).

1. Navigieren Sie zum Menü **Server > Settings**. Wechseln Sie in den *Web Server* Tab.
2. Wählen Sie den Benutzertyp, auf den den Sie den Zugriff einschränken möchten: *HTTPS - Restricted to AD users with Designer read access* oder *HTTPS - Restricted to custom users with Designer read access.*
![webserver settings](/img/content/xu/server-settings-security.png){:class="img-responsive"}
3. Klicken Sie den **[Select X.509 certificate]** Button. Das "Edit certificate location"-Fenster öffnet sich.
4. Wählen Sie das X.509 Zertifikat unter **Local Machine > Personal** aus.
5. Bestätigen Sie mit **[OK]**. Das Fenster schließt sich.
6. Optional: Ändern Sie die Port Nummer des *HTTPS Ports*.


### Zugriffsbeschränkung auf Windows AD Benutzer (Kerberos Authentifizierung) 

1. Weisen Sie den Xtract Universal/BoardConnector Dienst einem Windows Dienstkonto zu. Informationen finden Sie unter [Xtract Universal Dienst unter einem Windows Dienstkonto ausführen](./serversicherheit#einen-dienst-unter-einem-windows-dienstkonto-ausführen).
2. Aktivieren Sie die TLS Verschlüsselung wie in [Voraussetzungen: Aktivierung der TLS Verschlüsselung](./serversicherheit#voraussetzungen-aktivierung-der-tls-verschlüsselung) beschrieben.
3. Navigieren Sie zum Menü **Server > Settings**. Wählen Sie im *Web Server* Tab *HTTPS - Restricted to AD users with Designer read access*.
4. Wechseln Sie in den *Configuration Server* Tab.
5. Fügen Sie die Windows AD Benutzer und Benutzergruppen, die Extraktionen ausführen dürfen unter [*Access Management*](./benutzerverwaltung#zugriffssteuerung-auf-serverebene--server-settings) hinzu. 
6. Weisen Sie den Benutzern *Read* Erlaubnis zu.
7. Bestätigen Sie mit **[OK]**. Das Fenster schließt sich.
8. Wenn Sie dazu aufgefordert werden, starten Sie den Server neu.

Ergebnis: Eine Extraktion kann nur ausgeführt werden, wenn bei der Ausführung Windows AD Benutzerdaten mitgegeben werden und der übergebene Windows AD Benutzer *Read* Zugriff auf den Designer hat.

{: .box-note}
**Hinweis**: Diese Authentifizierung verwendet Kerberos Authentifizierung via SPNEGO. NTLM wird nicht unterstützt.



### Zugriffsbeschränkung auf benutzerdefinierte Benutzer (Basic Authentication)

1. Aktivieren Sie die TLS Verschlüsselung wie in [Voraussetzungen: Aktivierung der TLS Verschlüsselung](./serversicherheit#voraussetzungen-aktivierung-der-tls-verschlüsselung) beschrieben.
2. Navigieren Sie zum Menü **Server > Settings**. Wählen Sie im *Web Server* Tab *HTTPS - Restricted to custom users with Designer read access*.
2. Wechseln Sie in den *Configuration Server* Tab.
3. Fügen Sie die benutzerdefinierte Benutzer und Benutzergruppen, die Extraktionen ausführen dürfen unter [*Access Management*](./benutzerverwaltung#zugriffssteuerung-auf-serverebene--server-settings) hinzu. 
4. Weisen Sie den Benutzern *Read* Erlaubnis zu.
5. Bestätigen Sie mit **[OK]**. Das Fenster schließt sich.
6. Wenn Sie dazu aufgefordert werden, starten Sie den Server neu.

Ergebnis: Eine Extraktion kann nur ausgeführt werden, wenn bei der Ausführung die benutzerdefinierten Benutzerdaten mitgegeben werden und der Benutzer *Read* Zugriff auf den Designer hat.
