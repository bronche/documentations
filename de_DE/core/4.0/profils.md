Auf der Profilseite können Sie ein bestimmtes Verhalten von konfigurieren
Benutzerspezifisches Jeedom : Homepage-Themen der
Desktop-Version, mobile Version, Grafik ... Es erlaubt
auch um dein Passwort zu ändern.

Sie finden es oben rechts, indem Sie auf das Schneemannsymbol klicken
dann Profil (gefolgt von Ihrem Benutzernamen).

Themen
======

Im Themenbereich können Sie die Schnittstellenparameter anpassen :

-   **Desktop** : Themen, die im Desktop-Modus verwendet werden sollen, achten Sie nur auf die
    Das Standardthema wird offiziell von Jeedom unterstützt

-   **Farbe mobil** : ermöglicht die Auswahl der Schnittstellenfarbe
    (hier wird alles unterstützt)

-   **Desktop-Grafiken** : Mit dieser Option können Sie das Standarddesign für definieren
    Grafiken im Desktop-Modus

-   **Mobiler Graph** : Mit dieser Option können Sie das Standarddesign für definieren
    mobile Grafik

-   **Deckkraft durch Armaturenbrett-Widgets** : erlaubt, Deckkraft zu geben
    (zwischen 0 und 1) Widgets im Armaturenbrett

-   **Deckkraft durch Design-Widgets** : erlaubt, Deckkraft zu geben
    (zwischen 0 und 1) Widgets für Designs

-   **Deckkraft nach Ansichts-Widgets** : erlaubt, Deckkraft zu geben (zwischen
    0 und 1) Widgets in den Ansichten

-   **Deckkraft durch mobile Widgets** : erlaubt, Deckkraft zu geben
    (zwischen 0 und 1) mobile Widgets

Schnittstelle
---------

Ermöglicht das Definieren bestimmter Schnittstellenverhalten :

-   **General**

    -   **Menüs anzeigen** : Sagen Sie Jeedom, dass er das Panel anzeigen soll
        links, wenn es existiert, als Erinnerung ist dieses Panel
        verfügbar auf den meisten Plugin-Seiten sowie
        Seite mit Szenarien, Interaktionen, Objekten….

-   **Standardseite** : Standardseite, die angezeigt wird, wenn
    Desktop / Mobile-Verbindung

-   **Standardobjekt im Armaturenbrett** : Standardanzeigeobjekt
    bei der Ankunft auf dem Armaturenbrett / Handy

-   **Standardansicht** : Ansicht, die standardmäßig angezeigt wird, wenn Sie am ankommen
    das Armaturenbrett / Handy

-   **Standarddesign** : Design, das standardmäßig angezeigt wird, wenn
    die Ankunft auf dem Armaturenbrett / Handy

    -   **Vollbild** : Standardanzeige im Vollbildmodus, wenn
        die Ankunft auf den Entwürfen

-   **Armaturenbrett**

    -   **Klappen Sie das Szenario-Bedienfeld auf** : ermöglicht sichtbar zu machen
        Standardmäßig das Szenario-Menü (rechts) im Armaturenbrett

    -   **Klappen Sie das Objektfenster auf** : ermöglicht sichtbar zu machen durch
        Standardmäßig das Objektmenü (links) im Armaturenbrett

-   **Ansicht**

    -   **Klappen Sie das Ansichtsfenster auf** : ermöglicht sichtbar zu machen durch
        Standardansichtsmenü (links) für Ansichten

Sicherheit
--------

-   **2-stufige Authentifizierung** : ermöglicht zu konfigurieren
    2-Schritt-Authentifizierung (zur Erinnerung, dies ist ein sich ändernder Code
    wird alle X Sekunden in einer mobilen Anwendung angezeigt, geben Sie ein
    Google Authentifikator). Beachten Sie, dass eine doppelte Authentifizierung nur für externe Verbindungen angefordert wird. Für eine lokale Verbindung wird der Code daher nicht angefordert. Wichtig, wenn Sie während der Konfiguration der doppelten Authentifizierung einen Fehler haben, überprüfen Sie, ob jeedom (siehe auf der Gesundheitsseite) und Ihr Telefon gleichzeitig sind (1 Minute Unterschied reicht aus, damit es nicht funktioniert).

-   **Passwort** : ermöglicht es Ihnen, Ihr Passwort zu ändern (nicht
    vergessen Sie es unten erneut einzugeben)

-   **Benutzer-Hash** : Ihr Benutzer-API-Schlüssel

### Aktive Sitzungen

Hier haben Sie die Liste Ihrer aktuell verbundenen Sitzungen, deren ID,
ihre IP sowie das Datum der letzten Kommunikation. Durch Klicken auf
"Trennen "Dadurch wird der Benutzer getrennt. Achtung wenn es an ist
Bei einem registrierten Gerät wird die Aufzeichnung gelöscht.

### Registriertes Gerät

Hier finden Sie die Liste aller registrierten Geräte (welche sind
Verbindung ohne Authentifizierung) mit Ihrem Jeedom und dem Datum von
letzte Verwendung. Hier können Sie die Aufnahme von a löschen
peripher. Achtung, es trennt es nicht, sondern verhindert es nur
seine automatische Wiederverbindung.

Benachrichtigungen
-------------

-   **Benutzerbenachrichtigungsbefehl** : Standardbefehl für
    mach mit (Nachrichtentyp Befehl)
