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
-----------------------------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------------------------
E). 
Un OID (Object Identifier) es un identificador único en forma numérica jerárquica que se utiliza para identificar cada objeto o variable dentro de una base de datos de administración de red.

Relación con la MIB:

La MIB es una base de datos estructurada que contiene todos los objetos que pueden ser monitoreados o administrados en un dispositivo de red.

-La variable dentro de la MIB tiene asignado un OID único.
-El OID permite localizar y acceder a ese objeto específico dentro de la MIB.

SNMP para consultar los bytes recibidos;

Para saber la cantidad de bytes recibidos por una interfaz de red se utiliza la operación Get del protocolo SNMP.
La operación Get permite consultar o leer el valor de una variable específica en la MIB, como el contador de bytes recibidos de una interfaz.

El Trap no sería adecuado porque:

- Un Trap es un mensaje de notificación enviado automáticamente por el dispositivo cuando ocurre un evento.
- No sirve para consultar información específica bajo demanda.

Get: permite consultar el contador de bytes recibidos.
Trap: solo envía notificaciones de eventos, no consultas de información.
-----------------------------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------------------------
2). A).
La cabecera Ethernet es la encargada de la comunicación en la Capa 2 (Enlace de Datos) del modelo OSI. Según los datos de tu captura, estos son los componentes:

Destino (MAC)
Origen (MAC)
Tipo (EtherType)

El valor hexadecimal 0x0800 es un estándar fundamental en redes. Indica que el paquete de datos transportado dentro de esta trama Ethernet es un paquete IPv4 (Internet Protocol.

Función: Este campo permite al receptor saber a qué "pila" de protocolos debe enviar los datos una vez que se retira la cabecera Ethernet. Si el valor fuera, por ejemplo, 0x86DD, el receptor sabría que se trata de IPv6.

Relación con la captura: Puedes confirmar esto mirando la siguiente línea de tu imagen, donde efectivamente aparece: "Internet Protoco IPV4"
-----------------------------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------------------------
2). B).
Protocolo;

Este campo indica a qué protocolo de la Capa de Transporte (modelo OSI) deben entregarse los datos una vez que se procesa el paquete IP.
- En la captura: El valor es 6 (TCP).
- Significado: Esto le dice al sistema operativo que el contenido del paquete es un segmento Transmission Control Protocol. Si el valor fuera 17, indicaría UDP; si fuera 1, sería ICMP.

Campo: TTL (Time to Live);

El TTL o "Tiempo de Vida" es un contador que limita la existencia del paquete en la red para evitar que circule indefinidamente.

- Captura: El valor inicial es 128.
- Funcionamiento: Cada vez que el paquete atraviesa un router (un "salto"), este dispositivo resta 1 al valor del TTL. Si el valor llega a 0 antes de alcanzar su destino, el router descarta el paquete y suele enviar un mensaje de error (ICMP Time Exceeded) al emisor.

Es importante el TTL en la red.

Radica en la estabilidad y salud de la red:

- Prevención de bucles infinitos: Si existe un error de configuración en las tablas de enrutamiento, un paquete podría quedar atrapado girando entre dos o más routers para siempre. El TTL garantiza que el paquete sea destruido eventualmente, evitando que congestione el ancho de banda innecesariamente.

- Diagnóstico: Es la base de herramientas como traceroute, que utiliza paquetes con TTL incrementales para identificar cada salto en la ruta hacia un destino.
-----------------------------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------------------------
2). C).
1. Función de los Flags ACK y PSH.

Los "flags" o banderas son bits de control que indican el estado o la acción requerida para ese segmento específico.

ACK (Acknowledgment): Se utiliza para confirmar la recepción de datos. En este caso, el valor del campo "Acknowledgment Number: 1" indica que el emisor está confirmando que espera el siguiente byte del receptor.

PSH (Push): Indica a la pila TCP del receptor que debe pasar los datos a la aplicación de inmediato, en lugar de esperar a que el búfer se llene. Es común en tráfico interactivo o solicitudes HTTP para asegurar una respuesta rápida.

2. Puerto de Destino: 80

Puerto Destino: 80 es un indicador clave del servicio al que se intenta acceder en el servidor.

Identificación del Servicio: El puerto 80 es el puerto estándar asignado por la IANA para el protocolo HTTP (HyperText Transfer Protocol).

Indica que el cliente está intentando realizar una solicitud a un servidor web para obtener contenido no cifrado. Esto es consistente con la última línea de la captura, que muestra el método de aplicación.
-----------------------------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------------------------
2). D).
Transición a IPv6;

Si este paquete se enviara utilizando IPv6,

currirían los siguientes cambios estructurales:

Reemplazo de Cabecera: La cabecera IPv4 sería sustituida por la Cabecera Fija de IPv6, que es más sencilla (8 campos frente a los 12 o más de IPv4) y utiliza direcciones de 128 bits.

Mejora en el Procesamiento: Una de las mejoras más significativas es que los routers ya no calculan el Checksum (suma de comprobación) de la cabecera. En IPv6, se confía en que las capas superiores (como TCP) o las capas inferiores manejen la detección de errores, lo que reduce drásticamente la carga de procesamiento en cada salto y aumenta la velocidad de conmutación de los routers.
-----------------------------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------------------------
3). A).
Comando pathping;

Pathping 8.8.8.8.

A diferencia de un ping (conectividad básica) o un tracert (solo ruta), pathping combina ambos y añade estadísticas de pérdida de paquetes por cada salto. Proporciona un análisis detallado de la latencia (RTT) y el porcentaje de pérdida en cada nodo intermedio durante un periodo de tiempo.

Proceso que sigue pathping;

Fase de rastreo: Primero realiza un seguimiento de la ruta similar a tracert para identificar todos los routers en el camino.

Análisis: Una vez identificada la ruta, envía ráfagas de paquetes (pings) a cada router durante un tiempo determinado (por defecto, 250 milisegundos por salto).

Resultado: Finalmente, calcula y muestra el porcentaje de pérdida de paquetes en cada nodo, permitiendo identificar exactamente en qué punto de la red se está produciendo un fallo o congestión.

Anexo Captura del comando por CMD,

![Captura de pantalla 202klffjkf](https://github.com/user-attachments/assets/3a4c6e71-6cbe-4937-b16d-5bf979d66522)
-----------------------------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------------------------
3).B).

1). SNMP Walk;

Para "caminar" por el árbol MIB (Management Information Base), la herramienta estándar de línea de comandos es snmpwalk.

Aunque Windows no incluye esta herramienta de forma nativa en su instalación estándar, se utiliza comúnmente a través de la suite de herramientas Net-SNMP instalada en Windows. El comando específico para tu escenario sería:

snmpwalk -v 2c -c public 192.168.1.1 1.3.6.1.2.1.2
Desglose del comando:
snmpwalk: Indica que queremos recorrer una rama del árbol de forma secuencial.
-v 2c: Especifica que usaremos la versión 2c de SNMP.
-c public: Define la comunidad de solo lectura (community string).
192.168.1.1: La dirección IP del router.
1.3.6.1.2.1.2: Este es el OID (Object Identifier) para la rama de interfaces. Si quieres caminar por todo el árbol, podrías simplemente no poner el OID o usar .1.

2). Evento "authenticationFailure"

Un mensaje de trap tipo authenticationFailure se genera cuando el router recibe un mensaje SNMP con un nombre de comunidad incorrecto.

En tu caso, si alguien intentara consultar el router usando la comunidad "privado" en lugar de "public", el router enviaría esta alerta al gestor. Es una señal de advertencia de que un agente no autorizado (o mal configurado) está intentando acceder al dispositivo.

3). Ventajas de Trap vs. Polling (Consultas)

La diferencia fundamental radica en quién inicia la comunicación.

inciativa, uso de red , tiempo d erespuest, craga de CPU.

Ventaja del Trap: Es mucho más eficiente. Permite que el administrador de red se entere de un problema en el mismo segundo en que ocurre, sin necesidad de saturar el ancho de banda de la red.
-----------------------------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------------------------
4). 
1): Verificación de Conectividad y Resolución de Nombre (DNS)

Antes del envío, el sistema debe saber a qué dirección IP corresponde github

Capa OSI: Capa 7 (Aplicación) para la consulta y Capa 4 (Transporte) generalmente sobre UDP.
Protocolos y Estructuras: Protocolo DNS. Los datos se encapsulan en Datagramas (UDP).
Comandos de Red: * nslookup github.com: Para verificar que el servidor DNS resuelve la IP correctamente.
ping github.com: Para comprobar la latencia básica y conectividad ICMP.
Teletráfico: Una latencia alta en el DNS retrasará el inicio del viaje de los datos, dando la sensación de que el comando "se queda pegado".

Anexo Captura del comando ejecutado:

![Captura De Pantalla_01](https://github.com/user-attachments/assets/e4864d2c-2b94-47f1-a8ff-15335a4e3198)

![Captura De Pantalla_02](https://github.com/user-attachments/assets/5903f38f-c918-4ea1-89f8-e7c75659bfe9)

2): Establecimiento de la Conexión Segura (TCP + TLS/SSH)

git push requiere un canal confiable y cifrado para transmitir el código.

Capa OSI: Capa 4 (Transporte) y Capa 5/6 (Sesión/Presentación para el cifrado).
Protocolos y Estructuras: Protocolos TCP (puerto 443 o 22) y HTTPS/SSH. Los datos se organizan en Segmentos.
Comandos de Red: * netstat -an: Para verificar si la conexión con la IP de GitHub está en estado ESTABLISHED.
Filtro Wireshark: tcp.port == 443 para observar el saludo de tres vías (handshake).
Teletráfico: La pérdida de paquetes en este punto es crítica; si se pierde un segmento del handshake, la conexión fallará y el commit nunca saldrá de la máquina local.

3): Los Datos (Enrutamiento)

Una vez establecida la conexión, los segmentos de Git viajan por internet a través de múltiples nodos.

Capa OSI: Capa 3 (Red).
Protocolos y Estructuras: Protocolo IP (v4 o v6) e ICMP. Los datos viajan en Paquetes.
Comandos de Red: * tracert github.com: Para identificar en qué salto de la red se está produciendo un cuello de botella o caída.
pathping github.com: Combina ping y tracert para dar estadísticas detalladas de pérdida por salto.
Teletráfico: El Throughput (ancho de banda efectivo) determinará qué tan rápido se suben los archivos pesados. Un throughput bajo hará que la subida de la "nueva funcionalidad" sea lenta.

4): El Medio Físico;

Los bits finalmente se convierten en señales eléctricas, ópticas o de radio para salir de la oficina.

Capa OSI: Capa 2 (Enlace de datos) y Capa 1 (Física).
Protocolos y Estructuras: Ethernet o Wi-Fi. Los datos se convierten en Tramas (Frames) y finalmente en Bits.
Comandos de Red: * ipconfig /all: Para verificar que la puerta de enlace (Gateway) es alcanzable y la interfaz está activa.
Filtro Wireshark: eth.type == 0x0800 para ver el tráfico IP saliendo por la interfaz física.
Teletráfico: El ruido en el medio físico (interferencia en Wi-Fi) provoca pérdida de paquetes, obligando a TCP a retransmitir, lo que reduce drásticamente el éxito de la operación.
-----------------------------------------------------------------------------------------------------------------------------------------
-----------------------------------------------------------------------------------------------------------------------------------------
Estructurar la respuesta siguiendo la secuencia lógica de eventos:
Pasos 1 al 4;
Estructurar la
respuesta siguiendo la secuencia lógica de eventos
