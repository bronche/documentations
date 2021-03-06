Nützliche Pakete 
==============

Hier sind einige nützliche Pakete, um eine leere Installation durchzuführen :

-   **fail2ban** : Ermöglicht das Sperren von IPs, die versuchen, eine Verbindung herzustellen
    Maschine.

-   **vim** : Es ist ein Befehlszeilentexteditor
    Ersetzen Sie es auch durch Nano oder viele andere.

-   **net-tools** : Sammlung von Programmen zur Verwaltung des Netzwerks

-   **dos2unix** : Textkonvertierungswerkzeug

<!-- -->

    apt-get install -y vim fail2ban Netzwerkzeuge dos2unix

Wenn Sie mit VMware arbeiten, können Sie zusätzliche Tools hinzufügen
:

    apt-get install -y open-vm-tools

Färben Sie die Konsole 
====================

Wenn Sie möchten, dass Ihre Konsole (Bash) Farben verwendet :

    rm -rf /root/.bashrc
    wget https://raw.githubusercontent.com / jeedom / core / stabil / install / bashrc -O /root/.bashrc
    dos2unix /root/.bashrc

Root-Login in SSH zulassen 
==================================

Bearbeiten Sie die Datei / etc / ssh / sshd\_config und ändern Sie sie :

    PermitRootLogin ohne Passwort

Von :

    PermitRootLogin ja

> **Important**
>
> Stellen Sie sicher, dass Sie ein sicheres Root-Passwort verwenden ! Die Verwendung von
> fail2ban wird ebenfalls empfohlen.

Montieren Sie eine Samba-Freigabe 
=======================

Installation des cifs-Pakets

    apt-get install -y cifs-utils

Erstellen Sie den Einhängepunkt :

    mkdir / mnt / my_share

> **Note**
>
> Sie müssen meinen Anteil an Ihre Bedürfnisse anpassen

Mount in / etc / fstab hinzugefügt

    // IP_SERVER_SAMBA / mon_partage / mnt / mon_partage cifs uid = 0, rw, user = TODO, password = TODO 0 0

> **Note**
>
> Sie müssen die TODOs mit Ihrem Linux-Benutzernamen und Ihrem ändern
> Passwort

Übergang von Jessie zu Stretch 
===========================

Zum Testen des Upgrades und der Stretch-Installation mit Wiederherstellung
Als Backup bestätige ich, dass die Installation von Stretch by
Durch das Überschreiben sparen Sie Zeit.

-   **Methode 1 : Stretch-Installation :** Maximal 1 bis 2 Stunden und
    vor allem ein sauberes Betriebssystem.

-   **Methode 2 : Update von Jessie auf Stretch :** einen halben Tag um
    Wischen Sie Fehler ab.

Methode 1 : Installation von Stretch und Backup Restore 
-----------------------------------------------------------------

Bevor Sie beginnen, erstellen Sie eine vollständige Sicherung über Jeedom von Ihnen
Installation unter Jessie, dann exportieren Sie das Backup in ein anderes
Speichermedium.

> **Tip**
>
> Laden Sie das Backup nicht über die Weboberfläche (SSH, FTP) herunter,
> SAMBA, andere Ihrer Wahl), denn wenn Ihr Archiv groß ist
> Es kann leicht durch HTTP-Download beschädigt werden.
> Wenn es jedoch weniger als 100 MB beträgt, ist es spielbar.

-   Installieren Sie Debian Stretch auf Ihrer Box.

-   Konfigurieren Sie Ihr lokales Netzwerk neu und überprüfen Sie, ob Ihr Computer vorhanden ist
    betriebsbereit und aktuell.

-   Installieren Sie Jeedom, indem Sie dem Dokument folgen :
    <https://github.com/jeedom/documentation/blob/master/installation/de_DE/other.asciidoc>

\ [ACHTUNG \] MariaDB erlaubt keinen Zugriff mehr auf das 'root'-Profil, das
kann die Wiederherstellung einer Datenbank blockieren, die Sie haben
hat den Namen geändert (wie ich), damit wir den nicht sofort wiederherstellen
Backup. Wenn der Benutzer 'jeedom' nicht über die richtigen Berechtigungen verfügt, wird die
Wiederherstellung wird fehlschlagen.

Referenz :
<http://jc.etiemble.free.fr/abc/index.php/realisations/trucs-astuces/deb9php7>
(Kapitel 5a)

Kurz gesagt, 2 Befehlszeilen, um den Benutzer 'root' zu autorisieren
MYSQL unter Stretch :

    $ mysql -u root -p mysql
    Passwort eingeben:
    Willkommen auf dem MariaDB-Monitor.  Befehle enden mit; oder \ g.
    Ihre MariaDB-Verbindungs-ID lautet 2
    Serverversion: 10.1.21-MariaDB-5 Debian 9.0
    Copyright (c) 2000, 2016, Oracle, MariaDB Corporation Ab und andere.
    Geben Sie 'help' ein. oder '\ h' um Hilfe. Geben Sie '\ c' ein, um die aktuelle Eingabeanweisung zu löschen.

    MariaDB [MySQL]>
    MariaDB [MySQL]> GEWÄHRLEISTUNG FÜR ALLE PRIVILEGIEN *.* TO root @ 'localhost' IDENTIFIZIERT DURCH 'monpass';
    Abfrage OK, 0 Zeilen betroffen (0.00 Sek.)
    MariaDB [MySQL]> exit;
    Bye

> **Tip**
>
> Ersetzen Sie 'monpass' durch Ihr MYSQL-Passwort, das für das verwendet wird
> Root-Account unter "Debian 8 - Jessie". Ich gebe Root-Rechte
> vor allem, um meine Datenbanken mit 'PHPMYADMIN' zu verwalten, aber geben Sie sie an
> Der MYSQL-Benutzer 'jeedom' sollte ausreichen.

> **Tip**
>
> Das Passwort für den MYSQL jeedom-Benutzer finden Sie hier :
> Administration → Konfiguration → OS / DB → Datenbank

Es liegt an Ihnen, diesen Befehl entsprechend Ihrer Konfiguration anzupassen
früher :

    Gewähren Sie alle Privilegien auf *.* TO root @ 'localhost' IDENTIFIZIERT DURCH 'monpass';

ou

    Gewähren Sie alle Privilegien auf *.* TO jeedom @ 'localhost' IDENTIFIZIERT DURCH 'monpass';

-   Kopieren Sie Ihr Backup in den Ordner `/ var / www / html / backup`

-   Geben Sie die Rechte an www-Daten :
    `chown -R www-Daten: / var / www / html / backup / * `

-   Starten Sie die Wiederherstellung über die Jeedom-Oberfläche (Administration →
    Backups → Lokale Backups : Wählen Sie das richtige Backup
    und klicken Sie auf **Restaurer** gleich unten)

-   Warten Sie während der Wiederherstellung

-   Stellen Sie die Rechte an www-Daten auf allen Jeedom wieder her :
    `chown -R www-Daten: / var / www / html / `

-   Starten Sie die Box neu : `reboot`

-   Stellen Sie mit Ihren alten Kennungen über eine Verbindung zu Jeedom her
    Webinterface

-   Wechseln Sie zu jedem Plugin, um die Abhängigkeiten neu zu installieren (insbesondere
    auf denen, bei denen der Dämon "NOK" KO ist).

Methode 1 : Upgrade (weniger Erfolgschance) 
-----------------------------------------------

Betriebssystem-Update in der Jessie-Version.

    apt-get -y Update
    apt-get -y Upgrade
    apt-get -y dist-upgrade

Bearbeiten Sie die Datei / etc / apt / sources.Liste und ersetze alle
Jessie von Stretch macht mit vorheriger Dateisicherung :

    cp / etc / apt / sources.list /etc/apt/sources.list_backup
    sed -i 's / jessie / align / g' /etc/apt/sources.list

Betriebssystem-Update in der Stretch-Version.

    apt-get -y Update
    apt-get -y Upgrade
    apt-get -y dist-upgrade

Wechseln Sie zu MariaDB.

    apt-get -y installiere mariadb-server mariadb-client mariadb-common

Jeedom Update

    sh / var / www / html / install / install.sh -s 2
    sh / var / www / html / install / install.sh -s 5
    sh / var / www / html / install / install.sh -s 7
    sh / var / www / html / install / install.sh -s 10

Entfernen unnötiger Bibliotheken

    apt -y entferne `aptitude -F% p search '~ o' | grep -E -v ^ lib`
    apt -y entferne `aptitude -F% p search '~ o'`----

Notiz : Wenn Sie beim Öffnen Ihrer Jeedom-Seite einen PHP-Code erhalten, aktivieren Sie diesen, indem Sie die folgenden Befehle ausführen :

    a2enmod php7.0 
    systemctl starte apache2.service neu

