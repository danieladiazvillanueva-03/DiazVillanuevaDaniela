# Práctica 4: Unicast, broadcast y multicast en modo simulación

  

**Unidad 3:** Capa física y de enlace de datos

**Herramienta:** Cisco Packet Tracer

**Duración aproximada:** 35 a 40 minutos

  

## Objetivo

  

Observar cómo viajan las tramas Ethernet en una LAN y distinguir las comunicaciones unicast, broadcast y multicast a partir de la dirección MAC de destino.

  

## Material

  

Se reutiliza la red de la práctica 3: 1 switch 2960 y 4 PCs (PC0 a PC3) con las mismas IPs (192.168.1.1 a 192.168.1.4, máscara 255.255.255.0). Para el paso opcional se necesita un segundo switch 2960.

  

## Desarrollo

  

### Paso 1. Prepara la red

  

1. Abre tu archivo de la práctica 3, o arma la red de nuevo con las mismas IPs.

2. En cada PC, abre **Desktop → Command Prompt** y ejecuta:

  

   ```

   arp -d

   ```

  

   Esto borra la tabla ARP. Si no lo haces, el ARP no aparecerá en la simulación porque las PCs ya conocen las MAC de la práctica anterior.

3. En el switch, abre la pestaña **CLI**, escribe `enable` y ejecuta:

  

   ```

   clear mac address-table dynamic

   ```

  

   Así el switch parte sin MACs aprendidas.

4. Ten a la mano la tabla de MACs que anotaste en la práctica 3.

  

### Paso 2. Activa el modo simulación

  

1. En la esquina inferior derecha, cambia de **Realtime** a **Simulation**.

2. En el panel de simulación, abre **Edit Filters**. Deja activados solo **ARP** e **ICMP**.

  

### Paso 3. Genera tráfico

  

1. Selecciona la herramienta **Add Simple PDU** (el sobre cerrado en la barra de herramientas).

2. Haz clic en PC0 y luego en PC1. Se crea un evento en la lista.

3. Avanza paso a paso con el botón **Capture / Forward**.

4. Observa en la topología qué hace cada mensaje:

   - **Petición ARP:** sale de PC0 y el switch la manda a todos los demás puertos.

   - **Respuesta ARP:** regresa solo de PC1 a PC0.

   - **Eco ICMP (ping) y su respuesta:** viajan solo entre PC0 y PC1.

5. Anota qué PCs reciben cada mensaje y cuáles lo descartan (PC2 y PC3).

  

### Paso 4. Inspecciona cada trama

  

1. En la lista de eventos, haz clic en el cuadro de color de cada evento para abrir **PDU Information**.

2. Abre la pestaña **Outbound PDU Details** y baja hasta el encabezado **Ethernet II**.

3. Anota estos campos para cada trama: **DEST ADDR**, **SRC ADDR**, **TYPE** y **FCS**.

4. Lo que debes encontrar:

  

   | Mensaje | MAC destino | Tipo de envío |

   |---|---|---|

   | Petición ARP | FFFF.FFFF.FFFF | Broadcast |

   | Respuesta ARP | MAC de PC0 | Unicast |

   | Eco ICMP | MAC de PC1 | Unicast |

  

5. El FCS puede aparecer con valor `0x0`. Lo importante es identificar el campo, no su valor.

6. Haz clic en el sobre sobre el **switch** y abre la pestaña **OSI Model**. Verás que el switch solo procesa hasta la **capa 2**.

  

### Paso 5. Completa la tabla comparativa

  

| Trama | MAC origen | MAC destino | Tipo (unicast / broadcast) | ¿Quién la recibe? | ¿Quién la descarta? |

|---|---|---|---|---|---|

| Petición ARP | | | | | |

| Respuesta ARP | | | | | |

| Eco ICMP | | | | | |

  

### Paso 6 (opcional). Observa un multicast con CDP

  

1. Agrega un segundo switch 2960 y conéctalo al primero con cable cruzado (*Copper Cross-Over*) en el puerto Fa0/24 de ambos.

2. En el panel de simulación, activa el filtro **CDP**.

3. Avanza la simulación con **Auto Capture / Play** hasta que aparezca un evento CDP. Puede tardar unos segundos, porque los switches lo envían de forma periódica.

4. Abre el evento y revisa el **DEST ADDR**: debe ser `0100.0CCC.CCCC`, una dirección multicast.

5. Si el evento no aparece, avisa a tu profesor.

  

### Paso 7. Termina

  

1. Regresa a **Realtime** antes de guardar.

2. Guarda el archivo `.pkt`.

  

## Entregable

  

1. Capturas de pantalla de las tres tramas del Paso 4 (con los campos de Ethernet II visibles) y de la pestaña **OSI Model** del switch.

2. La tabla del Paso 5 completa.

3. Respuestas breves a estas preguntas:

   4. ¿Por qué la petición ARP va a FFFF.FFFF.FFFF?

   5. ¿Qué hace el switch con una trama broadcast y qué hace con una unicast cuando ya conoce la MAC destino?

   6. ¿Para qué sirve el FCS?

   7. ¿Por qué PC2 y PC3 reciben la petición ARP pero no el eco ICMP?

   8. ¿En qué capa trabaja el switch y cómo lo comprobaste?

9. El archivo `.pkt` guardado.