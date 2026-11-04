**Switch de capa 2**
Decide por dónde reenviar usando solo la dirección MAC de la trama y su tabla de direcciones MAC; trabaja dentro de una sola red (o una VLAN).

**Switch de capa 3**
Además de conmutar por MAC, puede enrutar usando la dirección IP del paquete y su tabla de rutas, y conecta varias redes o VLAN entre sí.

**Capa 2 frente a capa 3**

-Capa 2: lee la MAC, trabaja en una sola red, necesita un router para comunicar redes distintas y cuesta menos.

-Capa 3: lee MAC e IP, conecta varias redes o VLAN, enruta por sí mismo 

**¿Remplaza a un router?**
No del todo: el router sigue siendo mejor para conectar con el exterior (WAN, Internet) y para funciones como NAT. El switch de capa 3 se usa en campus y centros de datos para enrutar entre VLAN a alta velocidad.