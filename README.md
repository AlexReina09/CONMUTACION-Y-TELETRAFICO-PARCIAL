Latencia:
Es el tiempo que tarda un paquete de datos en viajar desde el emisor hasta el receptor y se mide normalmente en milisegundos (ms).

Jitter:
Es la variación en el tiempo de llegada de los paquetes que tardan en promedio 100 ms (latencia), si algunos llegan en 80 ms y otros en 150 ms es decir el retardo no es constante.

Afectaría mas negativamente el jitter,ya que un jitter alto provoca que se entrecorte la voz, audio robótico, palabras incompletas. 
el jitter altera la continuidad de una llamada.

-------------------------------------------------------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------------------------------------------------------

B). El protocolo UDP es mas eficiente por su throughput, y utiliza 8 bytes y el protocolo TCP utiliza mínimo 20 bytes.

Por lo cual UDP tiene menor sobrecarga de bytes. esto permite mayor throughput efectivo en la transmisión de video. 

- Envía más datos útiles por paquete.
- No usa mecanismos de confirmación.
- No retransmite paquetes.

y TCP ofrece mayor control de la perdida de paquetes,

- Un número de secuencia
- Detecta paquetes perdido.
- mantiene el orden correcto de los paquetes.
- mayor control de congestión en la red.

UDP no tiene este mecanismo de control, por lo cual si se pierde un paquete no se puede recuperar.
Más eficiente en throughput: UDP, por su cabecera más pequeña y menor sobrecarga, y mayor control de pérdida de paquetes: TCP,
por los campos adicionales en su cabecera.

-------------------------------------------------------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------------------------------------------------------
C). 
1. Protocolo que llena la tabla es la suite TCP/IP que llena esta tabla es ARP (Address Resolution Protocol).

2. Función principal de ARP es resolver una dirección IP en una dirección MAC dentro de una red local (LAN).
ARP actua como traductor de entre IP Y MAC.

3. Ralacion cuando los datos se envian por la red viajan dentro de una trama ethernet.
que contiene; 

Mac Destino, Mac Origen, Tipo,Datos,FCS

Relación con ARP:

ARP permite obtener la MAC destino necesaria para llenar el campo MAC destino de la trama Ethernet.
Sin ARP, el dispositivo no sabría a qué dirección física enviar la trama.
Relación con Ethernet: ARP permite completar el campo MAC destino de la trama Ethernet, haciendo posible el envío de datos en la red local.

-----------------------------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------------------------
D). 

1). SNMPv2c y SNMPv3 se diferencian principalmente en seguridad y en la gestión de mensajes.

SEGURIDAD
SNMPv2c:

Utiliza un mecanismo simple llamado community strings (como public o private) para el acceso.
No tiene cifrado.
No tiene autenticación fuerte.
Es vulnerable a interceptación o acceso no autorizado.

SNMPv3:
Incorpora seguridad avanzada:

Autenticación del usuario.
Cifrado de los mensajes (privacidad).
Integridad de datos para evitar modificaciones.
SNMPv3 es mucho más seguro que SNMPv2c.

2). Tipo de mensajes que manejan;

Ambos utilizan operaciones básicas de administración de red, como:

Get , Set, Trap , Response 

Diferencias:

SNMPv2c:
Maneja estos mensajes sin mecanismos de seguridad, usando únicamente la community string.

SNMPv3:
Los mismos mensajes se envían con autenticación y posible cifrado, gracias a su arquitectura de seguridad (USM y VACM).
