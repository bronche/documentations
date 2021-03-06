# Instalación en Raspberry Pi

Encontrará aquí la documentación para instalar Jeedom en una PI de frambuesa **con una tarjeta SD.**

> **Important**
>
> Debian 10 (Buster) es la distribución oficialmente compatible.

## Descargue la última imagen "lite""

[aquí](https://downloads.raspberrypi.org/raspbian_lite_latest)

## Grabe esta imagen en una SD con etcher, por ejemplo

[aquí](https://etcher.io/)

> **Note**
>
> Si usa Etcher para grabar su imagen, el paso de descompresión es inútil (el formato Zip se reconoce directamente en la selección del archivo de imagen).

## Habilitar acceso SSH

> **Warning**
>
> Por razones de seguridad, el acceso SSH ya no está habilitado de forma predeterminada en esta distribución. Entonces tienes que activarlo.

Se debe crear un archivo ssh vacío en la partición de arranque (el único accesible bajo Windows).

Solo haz clic derecho : documento nuevo / de texto y cámbiele el nombre a "ssh" **sin extensión**

> **Important**
>
> En Windows, en el explorador, por lo tanto, debe verificar su configuración en display / options / modificar la carpeta y las opciones de búsqueda /

![ExtensionFichier](images/ExtensionFichier.PNG)

## Comience el PI

Inserte su tarjeta SD, conecte el cable de red, conecte la alimentación.

## Conectarse en SSH

Identifica tu Pi en la red

Necesita saber la dirección IP de su PI. Varias soluciones :

-   Consulte la configuración de DHCP en su enrutador
-   Utilice un escáner de puertos de tipo angyipscanner" [aquí](http://angryip.org/download/#windows)

Establecer conexión

Luego use, por ejemplo, masilla para establecer su conexión [Aquí](http://www.putty.org/)

Ingrese la dirección IP de su PI (aquí 192.168.0.10) y haga clic en abrir. Acepte el mensaje de seguridad predeterminado al iniciar sesión por primera vez.

Inicie sesión con credenciales **pi / frambuesa**

> **Important**
>
> Por razones de seguridad, es imprescindible cambiar la contraseña predeterminada. Los casos de piratería basada en el uso del par de inicio de sesión / contraseña predeterminado de la Frambuesa están particularmente extendidos. (comando passwd y sudo passwd)

## Inicie el script de instalación de jeedom

``wget -O- https://raw.githubusercontent.com/jeedom/core/master/install/install.sh | sudo bash``

**La contraseña de sudo también es frambuesa**

> **Note**
>
> Dependiendo de su velocidad de internet, la instalación puede tomar de 45 a 90 minutos.. No debe interrumpir el proceso antes del final.. De lo contrario, tendrá que repetir todo el procedimiento..

Luego solo vaya a IP\_MACHINE\_JEEDOM

> **Note**
>
> Las credenciales predeterminadas son admin / admin

> **Note**
>
> Se pueden usar los siguientes argumentos : -w = carpeta del servidor web -z = dependencias de instalación z-wave -m = contraseña de root mysql deseada

````
./install.sh -w /var/www/html -z
````

## Optimizacion del sistema

Si usa su Raspberry for Jeedom sin una pantalla conectada, se recomienda llevar la RAM mínima en la parte de video.

Solo inicia sesión **SSH** y modificar el archivo de configuración : ``sudo nano /boot/config.txt``

Agregar **y O** Descomentar (quitando el #) **y O** Edita las lineas :

````
gpu_mem=16
disable_l2cache=0
gpu_freq=250
````

Salir guardando : ``CTRL+X`` después ``O`` después ``ENTER``

Reinicia tu RPI

Entonces puedes seguir la documentación [Primer paso con Jeedom](https://doc.jeedom.com/es_ES/premiers-pas/index)
