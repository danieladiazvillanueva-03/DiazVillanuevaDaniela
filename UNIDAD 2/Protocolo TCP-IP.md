---
aliases:
  - Protocolo TCP/IP
---
Modelo de cuatro capas que describe cómo se comunican los dispositivos en una red real; a diferencia de OSI, sí se implementa tal cual en Internet y en la mayoría de las redes actuales.

Nació del proyecto ARPANET en los años setenta, antes que el modelo OSI; por eso es el modelo práctico, construido desde la implementación y no desde la teoría.

### Capa de Aplicación
Es donde viven los programas y servicios que el usuario reconoce: navegación web, correo, mensajería. Agrupa lo que en OSI son tres capas separadas: aplicación, presentación y sesión.

### Capa de Transporte
Divide el mensaje en segmentos, agrega número de puerto de origen y destino, y decide si la entrega necesita confirmación (TCP) o no (UDP).

### Capa de Internet
Agrega las direcciones IP de origen y destino y es responsable de que el paquete encuentre su ruta entre redes distintas; aquí vive el protocolo IP.

### Capa de Acceso a la red
Agrega la dirección MAC del siguiente salto y convierte los datos en señal para el medio físico; agrupa lo que en OSI son las capas de enlace y física.