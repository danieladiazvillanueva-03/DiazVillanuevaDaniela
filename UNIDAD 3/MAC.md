**Dirección MAC**
La dirección MAC es el identificador de 48 bits que tiene cada tarjeta de red y que sirve para identificar el origen y el destino de una trama dentro de la LAN (capa 2).

**Cómo se escribe la MAC**
Se escribe con 12 dígitos hexadecimales, por ejemplo 00:1A:2B:3C:4D:5E. El formato cambia según el sistema: con guiones en Windows (00-1A-2B-3C-4D-5E) y con puntos en Cisco (001A.2B3C.4D5E).

**Estructura de la MAC**
Los primeros 24 bits (OUI) identifican al fabricante y los últimos 24 bits los asigna el fabricante a cada tarjeta, de modo que la dirección es única.

**Para qué sirve la MAC**
Los switches usan la MAC para decidir por qué puerto reenviar cada trama y construyen su tabla de direcciones aprendiendo la MAC de origen.

**La MAC se puede cambiar**
Viene grabada de fábrica en la tarjeta, pero el sistema operativo puede modificarla por software. Por eso no debe ser el único mecanismo de seguridad (MAC spoofing).

**Unicast, multicast y broadcast**
Según a cuántos equipos va dirigida, una comunicación puede ser unicast (a uno), multicast (a un grupo) o broadcast (a todos).

**Unicast: de uno a uno**
La trama va a un solo destinatario, identificado por su MAC específica; es el tipo de tráfico más común, como abrir una página web o copiar un archivo.

**Unicast en el switch**
El switch busca la MAC de destino en su tabla de direcciones y envía la trama solo por el puerto donde está ese equipo; si no la conoce, la inunda por todos los puertos.

**Multicast: de uno a un grupo**
La trama va a un grupo de equipos que se unieron a él; los demás la ignoran. En IPv4 usa direcciones 224.0.0.0 a 239.255.255.255 y MAC que empiezan con 01:00:5E.

**Multicast: ejemplos**
Se usa en video en vivo, IPTV y protocolos de enrutamiento como OS

**Broadcast: de uno a todos**
La trama llega  a todos los equipos de la red, con MAC de destino FF:FF:FF:FF:FF:FF; todos la reciben y la procesan.

**Dominio de broadcast**
Los routers no reenvían los broadcast 

Para qué sirve el unicast

Para qué sirve en multicast

Par qué sirve el broadcast