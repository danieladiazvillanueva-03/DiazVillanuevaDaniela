##### **Nombre: Daniela Díaz Villanueva**

### Campo 1
**Dato de ejemplo:** 10101010 10101010 10101010 10101010 10101010 10101010 10101010 10101011 (8 bytes)
**Nombre del campo:** Preámbulo.
**Para qué sirve:** Sincroniza al dispositivo que va a recibir los datos con la señal que está llegando.

### Campo 2
**Dato de ejemplo:** FFFF.FFFF.FFFF (6 bytes)
**Nombre del campo:** Dirección MAC de destino.
**Para qué sirve:** Identifica la dirección físcia (MAC) del dispositivo al que se dirige la trama.

### Campo 3
**Dato de ejemplo:** 0001.4321.ABCD (6 bytes)
**Nombre del campo:** Dirección MAC de origen.
**Para qué sirve:** Identifica la dirección física (MAC) del dispositivo del que se envía la trama.

### Campo 4
**Dato de ejemplo:** 0x0806 (2 bytes)
**Nombre del campo:** Tipo (EtherType).
**Para qué sirve:** Indica qué protocolo se transporta como el IPv4 o IPv6.

### Campo 5
**Dato de ejemplo:** ¿Quién tiene la IP 192.168.1.2? Responde a 192.168.1.1 (entre 46 y 1500 bytes)
**Nombre del campo:** Datos.
**Para qué sirve:** Es la información que se transporta, como un paquete IP. Si el paquete es muy pequeño, se usa padding (relleno) para alcanzar el tamaño mínimo.

### Campo 6
**Dato de ejemplo:** 0x3A7F91C2 (4 bytes)
**Nombre del campo:** FCS (Secuencia de verificación de trama).
**Para qué sirve:** Detecta errores en la trama mediante un cálculo CRC.
