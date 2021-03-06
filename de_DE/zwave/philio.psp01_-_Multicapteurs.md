Philio PSP01 
============

\.

-   **Das Modul**

\.

![module](images/philio.psp01/module.jpg)

\.

-   **Das Jeedom Visual**

\.

![vuedefaut1](images/philio.psp01/vuedefaut1.jpg)

\.

Zusammenfassung 
------

\.

Der PSP01-Detektor bietet 3 verschiedene Funktionen : Erkennung von
Bewegung, Temperatursensor und Lichtdetektor.

Dieser Detektor kann zur Sicherheit oder für verwendet werden
Automatisierung. Wenn der Detektor zugeordnet ist
Sicherheit dient es als Auslöser für Warnungen durch Erkennen
Änderungen der Infrarotstrahlung. Wenn eine Person
bewegt sich im Sichtfeld des Detektors, ist ein Funksignal
übertragen, was einen Alarm auslöst, um Eindringlinge abzuhalten.

Der Detektor kann auch in Kombination mit a verwendet werden
Z-Wave-Controller für die Heimautomation, indem beide erkannt werden
Änderungen der Infrarotstrahlung (Anwesenheit) und
Änderungen in der Helligkeit. Also können wir a auslösen
Beleuchtung, wenn Bewegung im Dunkeln erkannt wird.

Der Detektor erhöht auch die Helligkeit und die Temperatur, d.h.
signifikante Änderung, und jedes Mal, wenn eine Bewegung ist
erkannt. Ein Z-Wave-Controller (Fernbedienung, Dongle usw.) ist erforderlich
um diesen Detektor in Ihr Netzwerk zu integrieren, wenn Sie bereits einen haben
bestehendes Netzwerk.

\.

Funktionen 
---------

\.

-   3 in 1 Detektor: Bewegung, Temperatur, Licht

-   Nimmt den aktuellen Z-Wave 400series-Chip zur Unterstützung an
    Mehrkanalbetrieb und mehr Datendurchsatz
    hoch (9,6 / 40 / 100kbps)

-   Verwendet das Z-Wave 6.02 SDK

-   Optimierte Antennenreichweite

-   Verwendung für Hausautomations- oder Sicherheitsanwendungen

-   Taste zum Ein- / Ausschließen des Detektors

-   Autoprotection

-   Anzeige für niedrigen Batteriestand

-   Klein, diskret und ästhetisch

-   Benutzerfreundlichkeit und Installation

\.

Technische Daten 
---------------------------

\.

-   Modultyp : Z-Wave Sender

-   Versorgung : 1 CR123A 3V Batterie

-   Akkulaufzeit : 2 Jahre

-   Frequenz : 868.42 MHz

-   Übertragungsentfernung : 30m drinnen

-   Temperatursensor : -10 bis 70 ° C.

-   Helligkeitssensor : 0 bis 500 Lux

-   PIR-Erfassungswinkel : 90 °

-   PIR-Erfassungsbereich : 8 bis 10 m

-   Abmessungen : 28 x 96 x 23 mm

-   Gewicht : 39g

-   Betriebstemperatur : -10 bis 40 ° C.

-   Betriebsfeuchtigkeit : 85% rF max

-   CE-Norm : EN300 220-1

-   Z-Wave-Zertifizierung : ZC08-13050003

\.

Moduldaten 
-----------------

\.

-   Machen Sie : Philio Technology Corporation

-   Name : Philio PSP01

-   Hersteller ID : 316

-   Produkttyp : 2

-   Produkt-ID : 2

\.

Konfiguration 
-------------

\.

So konfigurieren Sie das OpenZwave-Plugin und wissen, wie Sie Jeedom einsetzen
Aufnahme beziehen sich darauf
[Dokumentation](https://jeedom.fr/doc/documentation/plugins/openzwave/de_DE/openzwave.html).

\.

> **Important**
>
> Um dieses Modul in den Einschlussmodus zu versetzen, drücken Sie die Taste dreimal
> Einschlussknopf gemäß seiner Papierdokumentation.

\.

![inclusion](images/philio.psp01/inclusion.jpg)

\.

Einmal enthalten, sollten Sie dies erhalten :

\.

![Plugin Zwave](images/philio.psp01/information.jpg)

\.

### Befehle 

\.

Sobald das Modul erkannt wurde, werden die dem Modul zugeordneten Befehle ausgeführt
disponibles.

\.

![Befehle](images/philio.psp01/commandes.jpg)

\.

Hier ist die Liste der Befehle :

\.

-   Präsenz : Es ist der Befehl, der eine Anwesenheitserkennung erkennt

-   Öffnung : Es ist der Befehl, der eine Erkennung auslöst
    d'ouverture

-   Temperatur : es ist der Befehl, der es erlaubt, die
    Temperatur

-   Helligkeit : Es ist der Befehl, der es ermöglicht, die Helligkeit zu erhöhen

-   Sabotage : Dies ist der Sabotagebefehl (er wird ausgelöst in
    herausreißen)

-   Batterie : Es ist der Batteriebefehl

\.

Alle Module des Bereichs haben die gleichen IDs. Es liegt an Ihnen, diese anzuzeigen
entsprechend Ihrem Modul.

### Konfiguration des Moduls 

\.

> **Important**
>
> Wecken Sie das Modul bei einer ersten Aufnahme immer gleich danach auf
> Einbeziehung.

\.

Dann, wenn Sie das Modul entsprechend konfigurieren möchten
Ihrer Installation müssen Sie durch die Schaltfläche gehen
"Konfiguration "des OpenZwave-Plugins von Jeedom.

\.

![Konfiguration plugin Zwave](images/plugin/bouton_configuration.jpg)

\.

Sie gelangen auf diese Seite (nachdem Sie auf die Registerkarte geklickt haben
Einstellungen)

\.

![Config1](images/philio.psp01/config1.jpg)

![Config2](images/philio.psp01/config2.jpg)

\.

Parameterdetails :

\.

-   2: Ermöglicht das Anpassen des an die Module in der Gruppe gesendeten Signals
    Verein 2

-   3: Stellt die Empfindlichkeit des Anwesenheitssensors ein (0 :
    deaktiviert 99: maximale Empfindlichkeit)

-   4: Stellt die Helligkeitsstufe ein, ab der die
    Das in Parameter 2 definierte Signal wird an die Module gesendet, die dem zugeordnet sind
    Gruppe 2

-   5: Betriebsmodus (nicht empfohlen, um ihn zu ändern : siehe
    auf der Dokumentation des Herstellers)

-   6: Multisensor-Betriebsmodus (nicht zum Ändern empfohlen
    : siehe Dokumentation des Herstellers)

-   9: Ermöglicht die Festlegung, wie lange das AUS-Signal dauern soll
    wird an Module gesendet, die der Gruppe 2 zugeordnet sind

-   10: Mit dieser Option können Sie die Dauer zwischen zwei Batterieberichten definieren (einer
    Einheit = 30 Minuten)

-   12: wird verwendet, um die Dauer zwischen zwei Helligkeitsberichten zu definieren
    (eine Einheit = 30 Minuten)

-   13: Ermöglicht die Definition der Zeit zwischen zwei Temperaturberichten
    (eine Einheit = 30 Minuten)

\.

### Gruppen 

\.

Dieses Modul hat zwei Zuordnungsgruppen, nur die erste
indispensable.

\.

![Groupe](images/philio.psp01/groupe.jpg)

\.

Gut zu wissen 
------------

\.

### Besonderheiten 

\.

> **Tip**
>
> Dieses Modul hat eine Besonderheit und keinen Bericht, der auf dem basiert
> Variationen, aber nur im Laufe der Zeit, sendet es alle seine Informationen an
> jede Erkennung. Es sendet das Signal auch mehrmals
> Anwesenheitserkennung folgt. Es ist daher ratsam, das Häkchen zu setzen
> Feld "Ereignis bei Änderung" auf der Anwesenheit, wenn Sie dies verwenden
> Befehl im Szenario-Trigger.

\.

### Alternative visuelle 

\.

![vuewidget](images/philio.psp01/vuewidget.jpg)

\.

Aufwachen 
------

\.

Um dieses Modul aufzuwecken, gibt es nur einen Weg :

-   Lassen Sie die Sabotage-Taste los und drücken Sie sie erneut

\.

Faq. 
------

\.

Dieses Modul wird durch Drücken der Sabotage-Taste aktiviert.

\.

Aktivieren Sie das Kontrollkästchen "Ereignis bei Änderung"".

\.

Dieses Modul ist ein Batteriemodul, die neue Konfiguration wird sein
beim nächsten Aufwachen berücksichtigt.

\.

Wichtiger Hinweis 
---------------

\.

> **Important**
>
> Sie müssen das Modul aufwecken : nach seiner Aufnahme, nach einer Änderung
> der Konfiguration, nach einer Änderung des Aufweckens, nach a
> Änderung der Assoziationsgruppen

\.

**@sarakha63**
