Link al repositorio: https://github.com/fferrlop/SimulacroRedes.git

# Parte 1: Conceptos y teoría

## Pregunta 1: Modelos OSI y TCP/IP

**a) Describe las principales diferencias entre el modelo OSI y el modelo TCP/IP**

Número de capas: el modelo OSI usa 7 capas (aplicación, presentación, sesión, transporte, red, enlace de datos, física) mientras que el modelo TCP/IP usan 4 (aplicación, transporte, internet, acceso red)

Orientación: El modelo OSI tiene un enfoque más teórico diseñado para hacer de guía. Por otro lado el TCP/IP es más práctico y funcional basado en protocolos reales.

Estandarización: El modelo OSI no está ligado a protocolos específicos y se centra en definir funciones por capa. En cambio, TCP/IP está directamente asociado a protocolos concretos como IP, TCP, UDP, HTTP, FTP.

Capa de aplicación: El modelo OSI divide la capa superior en 3 capas (Aplicación, Presentación y Sesión), mientras que TCP/IP agrupa esas funciones en una sola: la capa de aplicación.

**b) Explica brevemente las ventajas y limitaciones de cada uno de estos modelos.**

Diseño y enfoque: El modelo OSI fue diseñado como un marco teórico con siete capas bien diferenciadas, útil para la estandarización y análisis. En cambio, el modelo TCP/IP se desarrolló desde un enfoque práctico, orientado a su implementación real en redes de comunicación.

Separación de funciones: OSI define funciones específicas para cada capa, como presentación y sesión, lo que permite una separación técnica más detallada. TCP/IP agrupa esas funciones principalmente en la capa de aplicación, lo que reduce la claridad entre procesos pero simplifica la arquitectura.

Implementación práctica: TCP/IP es el modelo implementado en redes actuales y el que sustenta el funcionamiento de Internet. OSI, aunque estructurado conceptualmente, no se aplica directamente en sistemas reales.

Compatibilidad con protocolos: TCP/IP está asociado a protocolos reales como IP, TCP, UDP o HTTP, lo que facilita su uso operativo. OSI, al no definir protocolos específicos, funciona como modelo de referencia, pero no operativo.

Interacción entre capas: En OSI, las capas están diseñadas para funcionar de forma estrictamente jerárquica, con interfaces bien definidas. En TCP/IP, la interacción entre capas puede ser más flexible, lo que favorece la eficiencia en ciertas implementaciones, pero puede dificultar el aislamiento funcional.

Flexibilidad en el desarrollo: El modularidad del modelo OSI permite modificar o sustituir capas sin afectar al resto. En TCP/IP, la integración entre funciones dificulta una modificación aislada sin comprometer otras capas.

Estandarización y adopción: TCP/IP es el modelo universalmente adoptado en redes modernas. OSI, aunque más completo teóricamente, no logró implantarse en la práctica debido a su complejidad y falta de integración con protocolos existentes.

![_- visual selection (1)](https://github.com/user-attachments/assets/999963af-cb66-4496-a676-f954ef2e3d16)


## Pregunta 2: Función de la Capa de Transporte

La capa de transporte tiene como objetivo garantizar una comunicación extremo a extremo entre procesos de diferentes dispositivos. Se encarga de que los datos lleguen completos, en orden y sin errores, independientemente del tipo de red o de los dispositivos utilizados.

Segmentación y reensamblado: divide los datos en unidades más pequeñas llamadas segmentos y los reordena al llegar.

Control de errores: detecta y corrige errores mediante acuses de recibo y retransmisiones.

Control de flujo: regula la cantidad de datos enviados para no saturar al receptor.

Establecimiento y liberación de conexión: maneja el inicio y fin de la comunicación.

En el modelo OSI

La capa de transporte es la cuarta de las siete capas del modelo OSI. Su enfoque es teórico y está pensada para proporcionar una separación clara entre funciones, sin estar ligada a protocolos específicos.

Segmentación de datos y reensamblado.

Control de errores mediante confirmaciones y retransmisiones.

Control de flujo y manejo de congestión.

Establecimiento, mantenimiento y liberación de conexiones.

Protocolos teóricos asociados: TP0, TP1, TP2, TP3, TP4 (siendo TP4 el más robusto y confiable).

En el modelo TCP/IP

La capa de transporte en TCP/IP tiene una función práctica y operativa. Es responsable de la comunicación extremo a extremo y permite la transmisión de datos entre aplicaciones en diferentes dispositivos.

Multiplexación de datos mediante puertos.

Detección y corrección de errores.

Entrega ordenada (cuando se utiliza TCP).

Soporte para comunicaciones confiables o no confiables.

Protocolos asociados:

TCP (Transmission Control Protocol): proporciona conexión confiable, control de flujo y control de errores.

UDP (User Datagram Protocol): proporciona una transmisión rápida sin conexión ni garantía de entrega.

Comparación entre OSI y TCP/IP en la capa de transporte:

Modelo OSI: Modelo teórico con funciones bien definidas pero sin implementación práctica.

Modelo TCP/IP: Modelo funcional y operativo con protocolos ampliamente utilizados como TCP y UDP.

Separación de funciones: El OSI separa funciones como sesión y presentación en capas independientes, TCP/IP las agrupa en la capa de aplicación.

Fiabilidad: OSI incluye varios niveles de control teórico; TCP/IP ofrece fiabilidad práctica a través de TCP o rendimiento con UDP.

Ejemplos prácticos:

TCP se usa en navegación web (HTTP/HTTPS), correo electrónico (SMTP, IMAP) o transferencia de archivos (FTP).

UDP se usa en videollamadas, juegos en línea, DNS y transmisiones en tiempo real.

Protocolos asociados:

TP0, TP1, TP2, TP3, TP4 (Transport Protocols definidos por OSI).

De estos, TP4 es el más parecido a TCP y proporciona entrega fiable en redes no confiables.

## Pregunta 3: TCP vs. UDP

TCP (Transmission Control Protocol) y UDP (User Datagram Protocol) son dos protocolos de la capa de transporte del modelo TCP/IP. Ambos permiten la transmisión de datos entre aplicaciones, pero difieren significativamente en cómo gestionan la conexión, la fiabilidad y el control de errores. A continuación, se presentan sus principales diferencias:

Orientación a conexión: TCP es un protocolo orientado a conexión. Esto significa que establece una conexión previa entre el emisor y el receptor antes de transmitir datos (proceso de establecimiento de conexión con el 'three-way handshake'). UDP, en cambio, no establece conexión previa: envía los datos directamente, lo que lo convierte en un protocolo no orientado a conexión.

Fiabilidad y control de errores: TCP garantiza la entrega fiable de los datos. Utiliza mecanismos como confirmaciones de recepción (ACKs), control de errores, retransmisiones y ordenamiento de segmentos. UDP no ofrece ningún tipo de garantía: no confirma la recepción, no corrige errores ni asegura el orden.

Velocidad y orden de entrega: TCP es más lento debido a sus mecanismos de control y seguridad, pero asegura que los datos lleguen completos y en orden. UDP es más rápido, ya que no introduce sobrecarga por control de errores o confirmaciones, pero los datos pueden perderse o llegar desordenados.

Ejemplos de aplicaciones: TCP se utiliza en aplicaciones donde la fiabilidad y la integridad de los datos son esenciales, como navegación web (HTTP/HTTPS), transferencia de archivos (FTP), y correo electrónico (SMTP, IMAP). UDP se emplea en aplicaciones donde se prioriza la rapidez sobre la fiabilidad, como videollamadas, transmisión en tiempo real (streaming), videojuegos en línea y DNS.

## Pregunta 4: Protocolo para Transferencia de Archivos

**a) Protocolo tradicional:**

El protocolo tradicionalmente utilizado para la transferencia de archivos en redes TCP/IP es FTP (File Transfer Protocol). FTP permite la conexión entre un cliente y un servidor para subir, descargar o gestionar archivos a través de una red. Opera en modo texto por defecto y utiliza los puertos 20 (datos) y 21 (control).

**b) Alternativas a FTP:**

SFTP (SSH File Transfer Protocol): a diferencia de FTP, SFTP cifra toda la comunicación utilizando el protocolo SSH, lo que proporciona confidencialidad y seguridad en la transferencia de datos. Utiliza un único canal seguro (normalmente en el puerto 22) y es ampliamente utilizado para entornos que requieren protección frente a accesos no autorizados.

FTPS (FTP Secure): es una extensión de FTP que añade soporte para el cifrado mediante SSL/TLS. A diferencia de SFTP, que usa SSH, FTPS mantiene la estructura básica de FTP pero añade mecanismos de autenticación y cifrado, ofreciendo mayor seguridad en redes inseguras. Utiliza múltiples puertos para establecer y mantener la conexión segura.

## Pregunta 5: Resolución de Nombres en DNS

Cuando un usuario ingresa una URL en el navegador (por ejemplo, www.___.com), el sistema debe traducir ese nombre de dominio a una dirección IP que permita establecer la conexión con el servidor correspondiente. Este proceso se conoce como resolución de nombres DNS (Domain Name System). A continuación, se describe el proceso paso a paso:

1. Revisión de la caché local: El sistema operativo primero verifica si la dirección IP correspondiente al dominio solicitado ya se encuentra en la caché local. Si existe una entrada válida, se utiliza directamente sin realizar ninguna consulta adicional.

2. Consulta al servidor DNS del sistema (resolutor): Si la información no está en caché, el equipo envía una consulta al servidor DNS configurado (resolutor), generalmente proporcionado por el proveedor de servicios de Internet (ISP).

3. Verificación de la caché del servidor DNS: El servidor DNS consultado también revisa su propia caché para ver si tiene la respuesta almacenada. Si la tiene, responde inmediatamente al cliente.

4. Consulta recursiva (si no está en caché): Si el servidor DNS no tiene la dirección, inicia una consulta recursiva. Comienza preguntando a uno de los servidores raíz del DNS. Estos no conocen las IPs finales, pero dirigen la consulta hacia los servidores TLD (Top Level Domain), como .com, .org, .net.

5. Consulta a los servidores TLD: El servidor raíz responde con la dirección de un servidor TLD correspondiente al dominio (por ejemplo, para .com). Luego, el resolutor consulta al servidor TLD, que responde con la dirección del servidor autoritativo del dominio (por ejemplo, ejemplo.com).

6. Consulta al servidor autoritativo: El servidor autoritativo es el que tiene la información definitiva del dominio solicitado. Este responde con la dirección IP exacta asociada al nombre de dominio.

7. Respuesta al cliente: Una vez obtenida la dirección IP, el servidor DNS resolutor la envía al cliente, que puede ahora iniciar la conexión con el servidor web correspondiente.

8. Almacenamiento en caché: Para acelerar futuras solicitudes, tanto el cliente como los servidores intermedios almacenan la información en caché durante un tiempo determinado (TTL, Time to Live).

## Pregunta 6: Comunicación en el Modelo TCP/IP

El modelo TCP/IP describe cómo se comunican dos dispositivos a través de una red. Durante la transmisión de datos, cada capa del modelo cumple una función específica, desde que una aplicación genera los datos hasta que estos llegan al dispositivo receptor. A continuación, se detalla el papel de cada una de las capas en el proceso de envío y recepción:

1. Capa de Aplicación: Es la capa más cercana al usuario. Su función es proporcionar interfaces y servicios para aplicaciones de red como navegadores, correo electrónico, o clientes FTP. Los datos generados por estas aplicaciones se pasan a la capa de transporte. Ejemplos de protocolos en esta capa son HTTP, FTP, SMTP, y DNS.

2. Capa de Transporte: Su objetivo es proporcionar una comunicación extremo a extremo fiable o no fiable según el protocolo utilizado. Encapsula los datos de la capa de aplicación en segmentos, añade números de puerto para identificar las aplicaciones origen y destino, y puede controlar errores y retransmisiones. Protocolos comunes: TCP (confiable) y UDP (rápido pero no confiable).

3. Capa de Internet: Se encarga del direccionamiento lógico y el enrutamiento de los paquetes a través de redes interconectadas. Recibe los segmentos de la capa de transporte, los encapsula en datagramas IP, y determina la mejor ruta hacia el destino. El principal protocolo en esta capa es IP (Internet Protocol).

4. Capa de Acceso a Red: Incluye las funciones necesarias para transmitir físicamente los datos a través del medio de red (como cable, fibra o Wi-Fi). Se encarga de encapsular los datagramas IP en tramas, añadir direcciones físicas (MAC), y controlar el acceso al medio. Incluye protocolos como Ethernet, Wi-Fi, y ARP.

En el dispositivo receptor, el proceso se realiza en orden inverso. Cada capa extrae su encabezado y pasa los datos a la capa superior hasta que llegan a la aplicación correspondiente, permitiendo así la entrega correcta y completa del mensaje.

## Parte II: Capa Física y Ejercicios Prácticos

### Pregunta 7: Cálculo de Tasa de Transmisión Máxima (Fórmula de Shannon)

Utiliza la fórmula de Shannon:


Donde:

- **C** es la tasa de transmisión máxima (bps),
- **B** es el ancho de banda (Hz),
- **SNR** es la relación señal a ruido en escala lineal  
  (recuerda que:  
  `SNR (lineal) = 10^(SNR(dB) / 10)`)

---

**Enunciado:**

Calcula la tasa de transmisión máxima para un canal con las siguientes características:

- Ancho de banda: **500 MHz**
- SNR: **20 dB**

---

**Pasos:**

1. **Convertir SNR a escala lineal:**

SNR(lineal) = 10^(20 / 10) = 100

2. **Aplicar la fórmula de Shannon:**

C = 500 × 10⁶ × log₂(1 + 100) = 500 × 10⁶ × log₂(101) ≈ 500 × 10⁶ × 6.6582 ≈ 3.33 × 10⁹ bps

---

**Resultado:**

La tasa de transmisión máxima es aproximadamente **3.33 Gbps**.


