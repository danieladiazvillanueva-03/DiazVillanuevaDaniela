**IPv4**
	IPv4 es el producto de la capa de red que direcciona y enruta los paquetes entre redes, usando direcciones de 32 bits (unos 4,300 millones en total).

**Historia de IPv4**
	IPv4 se definió en 1981 (RFC 791) dentro de la familia TCP/IP , diseñada por Vint Cerf y Bob Kahn.
	En 1983 ARPANET adoptó TCP/IP, el origen de lo que hoy es Internet.

**Cómo se agotaron las direcciones**
	Las 4,300 millones de direcciones parecían suficientes, pero se repitieron en bloques por clases: una Clase A daba más de 16 millones a una sola organización. Además, los dispositivos conectados crecieron sin parar.
	En 2011 la IANA entregó sus últimos bloques a los registros regionales. Se alargó la vida de IPv4 con CIDR, las direcciones privadas y NAT; la solución definitivo es IPv6.

**Diferencias entre IP pública e IP privada**
	La diferencia principal es el alcance que tienen dentro de una red y en Internet.
	Ambas son direcciones IP que identifican dispositivos, pero se utilizan para propósitos diferentes.
	-La IP pública es una dirección IP que identifica tu conexión o red frente a Internet.
	-La IP privada es una dirección IP que se utiliza dentro de una red local (LAN), por ejemplo en tu casa, escuela o empresa.

**Qué es IANA**
	Internet Assigned Numbers Authority es una organización que se encarga de coordinar y administrar elementos fundamentales del funcionamiento de Internet, especialmente la asignación de identificadores únicos.
	Sus principales funciones son:
		-Administración de direcciones IP
		-Administración de nombres de dominio
		-Asignación de números de protocolo
		-Identificadores únicos

**Características de IPv4**
	Es sin conexión (cada paquete viaja por separado), de mejor esfuerzo (no garantiza la entrega) e independientemente del medio (funciona sobre cobre, fibra o Wi-Fi).

**Encabezado IPv4**
	El encabezado mide 20 bytes como mínimo y lleva la IP de origen, la IP de destino, el TTL (límite de saltos) y el campo protocolo (TCP, UDP o ICMP).

**IPv6**
	IPv6 usa direcciones de 128 bits y se creó porque las direcciones IPv4 se agotaron; permite un número prácticamente ilimitado de dispositivos.

**Cuántas direcciones tiene IPv6**
	Con 128 bits hay 2^128 direcciones: unos 340 sextillones (3.4 *  10^38), es decir, 2^96 veces más que IPv4.
	Cada subred estándar (/64) por sí sola tiene 2^64 direcciones, más de 18 trillones.

**Ventajas de IPv6**
	Ofrece un espacio de direcciones enorme, un encabezado simplificado de 40 bytes, autoconfiguración de direcciones y no usa broadcast: lo reemplaza el multicast.

**División de la red en grupos**
	Una red grande se divide en subredes: grupos de dispositivos organizados por ubicación, función o departamento, cada unos con su propio rango de direcciones.

**Por qué se tiene que dividir una red**
	Al dividir se reduce el tráfico de broadcast, mejora el rendimiento, se aplican políticas de seguridad por grupo y se facilita la administración.

