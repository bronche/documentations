Useful packages 
==============

Here are some useful packages to put on a blank installation :

-   **fail2ban** : Allows yor to ban IPs who try to connect
    machine.

-   **vim** : It's a command line text editor, yor can
    also replace it with nano or many others.

-   **net-tools** : collection of programs to manage the network

-   **dos2unix** : text conversion tool

<!-- -->

    apt-get install -y vim fail2ban net-tools dos2unix

If yor are on VMware, yor can add additional tools
:

    apt-get install -y open-vm-tools

Colorize the console 
====================

If yor want your console (bash) to use colors :

    rm -rf /root/.bashrc
    wget https://raw.githubusercontent.com / jeedom / core / stable / install / bashrc -O /root/.bashrc
    dos2unix /root/.bashrc

Allow root login in SSH 
==================================

Edit the file / etc / ssh / sshd\_config and change :

    PermitRootLogin without-password

By :

    PermitRootLogin yes

> **Important**
>
> Be sure to use a strong root password ! The use of
> fail2ban is also recommended.

Mount a Samba share 
=======================

Installation of the cifs package

    apt-get install -y cifs-utils

Create the mount point :

    mkdir / mnt / my_share

> **Note**
>
> Yor have to adapt my share according to your needs

Added mount in / etc / fstab

    // IP_SERVER_SAMBA / my_sharing / mnt / my_sharing cifs uid = 0, rw, user = TODO, password = TODO 0 0

> **Note**
>
> Yor must change the TODOs with your linux username and your
> Password

Transition from Jessie to Stretch 
===========================

For having tested the upgrade and the Stretch installation with restoration
a backup, I confirm that the installation of Stretch by
overwriting will save yor time.

-   **Method 1 : Stretch installation :** 1 to 2 hours maximum, and
    especially a clean operating system.

-   **Method 2 : update from Jessie to Stretch :** half a day at
    wipe bugs.

Method 1 : Installation of Stretch and backup restore 
-----------------------------------------------------------------

Before yor start, make a full backup via Jeedom of your
installation under Jessie, then export the backup to another
storage medium.

> **Tip**
>
> Download the backup other than through the web interface (SSH, FTP,
> SAMBA, others of your choice), because if your archive is large
> it can easily get corrupted via HTTP download.
> However, if it is less than 100MB, it is playable.

-   Install Debian Stretch on your box.

-   Reconfigure your local network, check that your machine is
    operational and up to date.

-   Install Jeedom by following the doc :
    <https://github.com/jeedom/documentation/blob/master/installation/en_US/other.asciidoc>

\ [ATTENTION \] MariaDB no longer allows access to the 'root' profile, which
can block the restoration of a database that yor have
changed the name (like me) so we don't immediately restore the
backup. If the user 'jeedom' does not have the correct permissions, the
restoration will fail.

Reference :
<http://jc.etiemble.free.fr/abc/index.php/realisations/trucs-astuces/deb9php7>
(chapter 5a)

In short, 2 command lines to authorize the user 'root' in
MYSQL, under Stretch :

    $ mysql -u root -p mysql
    Enter password:
    Welcome to the MariaDB monitor.  Commands end with; or \ g.
    Your MariaDB connection id is 2
    Server version: 10.1.21-MariaDB-5 Debian 9.0
    Copyright (c) 2000, 2016, Oracle, MariaDB Corporation Ab and others.
    Type 'help;' or '\ h' for help. Type '\ c' to clear the current input statement.

    MariaDB [mysql]>
    MariaDB [mysql]> GRANT ALL PRIVILEGES ON *.* TO root @ 'localhost' IDENTIFIED BY 'monpass';
    Query OK, 0 rows affected (0.00 sec)
    MariaDB [mysql]> exit;
    Bye

> **Tip**
>
> Replace 'monpass' with your MYSQL password used for the
> root account under "Debian 8 - Jessie". I give root rights
> especially to manage my databases with 'PHPMYADMIN', but give them to
> the MYSQL user 'jeedom' should suffice.

> **Tip**
>
> Yor will find the password for the MYSQL jeedom user here :
> Administration → Configuration → OS / DB → Database

It's up to yor to adapt this command according to your configuration
previous :

    GRANT ALL PRIVILEGES ON *.* TO root @ 'localhost' IDENTIFIED BY 'monpass';

ou

    GRANT ALL PRIVILEGES ON *.* TO jeedom @ 'localhost' IDENTIFIED BY 'monpass';

-   Copy your backup to the `/ var / www / html / backup` folder

-   Give the rights to www-data :
    `chown -R www-data: / var / www / html / backup / * `

-   Launch the restoration via the Jeedom interface (Administration →
    Backups → Local Backups : Choose the right backup
    and click **Restaurer** just below)

-   Wait during the restoration

-   Restore rights to www-data on all Jeedom :
    `chown -R www-data: / var / www / html / `

-   Restart the box : `reboot`

-   Connect to Jeedom with your old identifiers via
    web interface

-   Switch to each plugin to reinstall the dependencies (in particular
    on those where the daemon is "NOK" KO).

Method 1 : Upgrade (less chance of success) 
-----------------------------------------------

OS update in Jessie version.

    apt-get -y update
    apt-get -y upgrade
    apt-get -y dist-upgrade

Edit the / etc / apt / sources file.list and replace all
Jessie by Stretch, with prior file backup, doing :

    cp / etc / apt / sources.list /etc/apt/sources.list_backup
    sed -i 's / jessie / stretch / g' /etc/apt/sources.list

OS update in Stretch version.

    apt-get -y update
    apt-get -y upgrade
    apt-get -y dist-upgrade

Switch to MariaDB.

    apt-get -y install mariadb-server mariadb-client mariadb-common

Jeedom update

    sh / var / www / html / install / install.sh -s 2
    sh / var / www / html / install / install.sh -s 5
    sh / var / www / html / install / install.sh -s 7
    sh / var / www / html / install / install.sh -s 10

Removal of unnecessary libraries

    apt -y remove `aptitude -F% p search '~ o' | grep -E -v ^ lib`
    apt -y remove `aptitude -F% p search '~ o'`----

NOTE : If when yor open your Jeedom page yor get a php code, activate it by running the following commands :

    a2enmod php7.0 
    systemctl restart apache2.service

