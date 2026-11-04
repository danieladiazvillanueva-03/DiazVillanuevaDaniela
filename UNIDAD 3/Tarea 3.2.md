# Práctica 3: Tabla de direcciones MAC del switch

  

**Unidad 3:** Capa física y de enlace de datos

**Herramienta:** Cisco Packet Tracer

**Duración aproximada:** 25 a 30 minutos

  

## Objetivo

  

Observar cómo un switch aprende las direcciones MAC de los dispositivos conectados y las asocia con sus puertos.

  

## Material

  

- 1 switch 2960

- 4 PCs (PC0 a PC3)

  

## Desarrollo

  

### Paso 1. Arma la red

  

1. Coloca un switch 2960 y 4 PCs (PC0 a PC3).

2. Conecta cada PC al switch con cable directo (*Copper Straight-Through*):

  

   | PC | Puerto del switch |

   |---|---|

   | PC0 | Fa0/1 |

   | PC1 | Fa0/2 |

   | PC2 | Fa0/3 |

   | PC3 | Fa0/4 |

  

3. Espera a que los enlaces se pongan en verde.

  

### Paso 2. Asigna las IPs

  

En cada PC, entra a **Desktop → IP Configuration** y escribe:

  

| PC | IP | Máscara |

|---|---|---|

| PC0 | 192.168.1.1 | 255.255.255.0 |

| PC1 | 192.168.1.2 | 255.255.255.0 |

| PC2 | 192.168.1.3 | 255.255.255.0 |

| PC3 | 192.168.1.4 | 255.255.255.0 |

  

> Las IPs solo sirven para poder hacer ping. Lo que se analiza en esta práctica son las direcciones MAC.

  

### Paso 3. Anota la MAC de cada PC

  

1. En cada PC, abre **Desktop → Command Prompt**.

2. Escribe `ipconfig /all`.

3. Copia la **Physical Address** de cada PC en una tabla con estas columnas: PC, puerto del switch y MAC.

  

### Paso 4. Revisa la tabla del switch antes de enviar tráfico

  

1. Haz clic en el switch y abre la pestaña **CLI**.

2. Presiona Enter, escribe `enable` y presiona Enter.

3. Escribe:

  

   ```

   show mac address-table

   ```

  

   Si el comando no se reconoce, usa `show mac-address-table`.

4. Toma una captura de pantalla. La tabla debería estar vacía o casi vacía, porque el switch todavía no ha visto tramas.

  

### Paso 5. Genera tráfico entre dos PCs

  

1. En PC0, abre **Command Prompt** y ejecuta:

  

   ```

   ping 192.168.1.2

   ```

  

2. El primer ping puede fallar con "Request timed out". Es normal: PC0 primero necesita conocer la MAC de PC1 mediante ARP.

3. Ejecuta el ping otra vez hasta que responda.

  

### Paso 6. Revisa la tabla otra vez

  

1. Regresa al CLI del switch y ejecuta `show mac address-table`.

2. Deben aparecer las MAC de PC0 y PC1, cada una asociada a su puerto (Fa0/1 y Fa0/2), con tipo **DYNAMIC** y VLAN 1.

3. Toma otra captura de pantalla.

  

### Paso 7. Completa la tabla

  

1. Desde PC2, haz ping a PC3:

  

   ```

   ping 192.168.1.4

   ```

  

2. Revisa la tabla del switch una tercera vez.

3. Ahora deben aparecer las 4 MAC, cada una en su puerto.

4. Compara contra las MAC que anotaste en el paso 3: deben coincidir. Toma una captura.

  

### Paso 8 (opcional). Borra la tabla y observa cómo se aprende de nuevo

  

1. En el CLI del switch, ejecuta:

  

   ```

   clear mac address-table dynamic

   ```

  

2. Ejecuta `show mac address-table`: la tabla debe estar vacía otra vez.

3. Haz un ping entre dos PCs y consulta la tabla de nuevo: el switch vuelve a aprender las MAC.

  

## Entregable

  

1. Capturas de pantalla de la tabla del switch en tres momentos: paso 4 (antes del ping), paso 6 (después del primer ping) y paso 7 (con las 4 MAC).

2. La tabla escrita con PC, puerto del switch y MAC.

3. Respuestas breves a estas preguntas:

   4. ¿De dónde aprende el switch las direcciones MAC?

   5. ¿Por qué falló el primer ping?

   6. ¿Qué tipo de entrada (dinámica o estática) tiene cada MAC y qué significa?

7. Guarda tu archivo de Packet Tracer (`.pkt`) y entrégalo junto con lo anterior.