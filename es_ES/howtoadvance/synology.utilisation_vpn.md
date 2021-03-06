Instalar servidor VPN 
====================

Desde un navegador web en una computadora conectada a la misma red que
Synology

Vaya a la interfaz DSM e inicie sesión con una cuenta de administrador y luego
vaya al menú principal y seleccione Centro de paquetes

Arriba a la izquierda en la ventana, haga una búsqueda con la palabra VPN.
El servidor VPN debería aparecer, luego haga clic en instalar.

![synology.utilisation vpn1](images/synology.utilisation_vpn1.png)

Regrese al menú principal y seleccione Servidor VPN

![synology.utilisation vpn2](images/synology.utilisation_vpn2.png)

Cuando se abra la ventana, vaya a L2TP / IPSEC

Elija la opción Habilitar servidor VPN L2TP / IPsec

En Dirección IP dinámica, ingrese un número que corresponderá al sub
red para asignar las IP de sus dispositivos en VPN en la red interna
desde tu lugar. NB : no elijas lo mismo que el
subred predeterminada de su caja ex en libre la subred de
máquinas es 192.168.1.0 así que en el ejemplo ponemos 2

Luego ingrese el número máximo de conexiones que desea permitir
en el servidor VPN, entonces el número máximo de conexiones simultáneas
para un usuario

Finalmente ingrese una clave para compartir NB : es una contraseña que él
tendrá que ingresar la configuración de VPN en el móvil o tableta.

Luego aplique

![synology.utilisation vpn3](images/synology.utilisation_vpn3.png)

Luego, un mensaje indica los puertos que deben redirigirse en su
Caja de Internet a su NAS.

![synology.utilisation vpn4](images/synology.utilisation_vpn4.png)

Permitir a los usuarios usar el servicio VPN en el NAS 
===============================================================

Regrese al menú principal y seleccione Servidor VPN

![synology.utilisation vpn2](images/synology.utilisation_vpn2.png)

En la parte izquierda, seleccione Privilegio

Desmarque todas las casillas bajo PPTP Open VPN y L2TP

Marque solo la casilla en frente del usuario que desea
permitir usar VPN .

> **Tip**
>
> Es recomendable crear un usuario solo para la VPN
> y sin ningún otro derecho / autorización que hacer con la VPN.

![synology.utilisation vpn5](images/synology.utilisation_vpn5.png)

Redireccionar los puertos de su BOX 
===============================

En el navegador ingrese 192.168.1.1. Haga clic en configuración
Freebox

![synology.utilisation vpn6](images/synology.utilisation_vpn6.png)

Seleccionar modo avanzado

![synology.utilisation vpn7](images/synology.utilisation_vpn7.png)

Seleccione Port Management

![synology.utilisation vpn8](images/synology.utilisation_vpn8.png)

Agregar una redirección

![synology.utilisation vpn9](images/synology.utilisation_vpn9.png)

Ingrese los parámetros de la siguiente manera.

> **Tip**
>
> El ID de destino es lo único que depende de su instalación,
> debe poner la IP de su Synology NAS

Guardar

![synology.utilisation vpn10](images/synology.utilisation_vpn10.png)

Luego observamos que la configuración se tiene en cuenta

![synology.utilisation vpn11](images/synology.utilisation_vpn11.png)

Repita la operación con los puertos UDP 500 y 4500

Configura la VPN en tu móvil 
==================================

Vaya a la aplicación y seleccione Configuración

![synology.utilisation vpn12](images/synology.utilisation_vpn12.png)

Haga clic en… Más

![synology.utilisation vpn13](images/synology.utilisation_vpn13.png)

Haga clic en VPN

![synology.utilisation vpn14](images/synology.utilisation_vpn14.png)

Haga clic en el + en la esquina superior derecha

![synology.utilisation vpn15](images/synology.utilisation_vpn15.png)

Dé un nombre al acceso VPN, establezca como tipo L2TP / IPSec PSK, ingrese
la dirección pública de su casilla de internet (o un nombre DNS si tiene uno
a) e ingrese la clave compartida ingresada en la sección Configurar una
Servidor VPN :

![synology.utilisation vpn16](images/synology.utilisation_vpn16.png)

Ahora para iniciar la VPN, simplemente haga clic en el nuevo
línea que apareció con el nombre de tu túnel VPN

![synology.utilisation vpn17](images/synology.utilisation_vpn17.png)

Luego ingrese el nombre de usuario y la contraseña del usuario que fue
configurado en la sección Configurar un servidor VPN

![synology.utilisation vpn18](images/synology.utilisation_vpn18.png)

Y eso es todo lo que haces en tu teléfono, es como tú
estaban en WiFi desde casa !
