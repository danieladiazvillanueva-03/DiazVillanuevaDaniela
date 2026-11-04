---
aliases:
  - Modelo TCP/IP
---
### Componentes
La capa física se compone de tres elementos: los medios físicos (cables, conectores y dispositivos), la codificación de los datos y la señalización que los transmite.

### Parámetros
Su desempeño se mide con tres parámetros: el ancho de banda (capacidad máxima), el rendimiento (lo que realmente se transfiere) y la latencia (el retardo en llegar).

### Tipos de cable: 
#### Cobre
El cable de cobre de par trenzado (UTP) transmite señales eléctricas con conector RJ-45, alcanza hasta 100 metros y es el más usado en LAN; el trenzado reduce la interferencia.
![[Pasted image 20261020193928.png|337]]

#### UTP: ¿por qué los cables van en pares?
Los 8 hilos del UTP forman 4 pares trenzados. Cada par envía la señal con polaridad opuesta en sus dos hilos; la interferencia afecta a ambos por igual y el receptor la cancela al comparar los dos.
Cada par tiene un trenzado distinto para reducir la diafonía entre pares vecinos.
![[Pasted image 20261020193426.png|337]]

#### Fibra óptica
La fibra ótica transmite pulsos de luz: llega a mayores distancias y es inmune a la interferencia electromagnética, pero es más costosa y delicada de instalar.
![[Pasted image 20261020194158.png|343]]

#### Medios inalámbricos
Transmiten por ondas de radio (Wi-Fi, Bluetooth, celular); dan movilidad, pero el medio es compartido, sufre interferencia y requiere mediadas de seguridad.
![[Pasted image 20261020200055.png|344]]

### Señales de comunicación
Una señal es una variación de una propiedad física que representa bits: cambios de voltaje en cobre, pulsos de luz en fibra u ondas de radio en el aire.

### Señalización y codificación física
La codificación convierte los bits en un patrón predefinido que facilita la sincronía y la detección de errores; la señalización define cómo se representa ese patrón en el medio.

### Conexión de la comunicación
Un dispositivo se conecta mediante su tarjeta de red (NIC), un puerto, un conector y el medio; la NIC convierte los bits en la señal que el medio puede transportar.

## Ethernet capa 1 y 2

Ethernet (IEEE 802.3) es el estándar dominante en LAN y trabaja en dos capas: en la capa 1 define medios y señalización, y en la capa 2 define las tramas y las direcciones MAC.

ARP: de dirección IP a dirección MAC
El protocolo ARP permite descubrir la dirección MAC de un dispositivo a partir de su dirección IP.  Envía una petición por broadcast; solo el dueño de esa IP responde por unicast, y el resultado se guarda en la tabla ARP.

Envenenamiento ARP (ARP poisoning)
ARP no verifica quién responde: un atacante envía respuestas ARP falsas para que otros equipos asocien su MAC con la IP de dispositivo, por ejemplo la del router, y así intercepta el tráfico (ataque de intermediario).
Se mitiga con inspección dinámica de ARP (DAI) en el switch y con entradas ARP estáticas en los equipos críticos.