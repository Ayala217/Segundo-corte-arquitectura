# Problemas identificados en la infraestructura de RedExpress

1. **Latencia en el envío de información**

Los datos obtenidos a partir de los servicios de tracking, alertas, gestión de paquetes y procesamiento de rutas pueden tardar en llegar a los servidores regionales en caso de que los servidores estén ubicados en una zona lejana de la nube.
Esto podría causar una ralentización en el funcionamiento del sistema, afectando a la experiencia y satisfacción del usuario.

**Solución**

Una posible solución podría ser aplicar una arquitectura multirregional además de llevar a cabo la replicación de datos y servicios que estén localizados cerca del usuario. 
Los servicios de seguimiento, enrutado de paquetes y paquete emitir, tienen la posibilidad de ser distribuidos en varios servidores regionales de la nube, lo que permite que cada usuario o mensajero se asocie de forma automática al servidor más cercano, desde el punto de vista geográfico.

2. **Cuello de botella**

En los servicios en la nube presentados en la arquitectura, el procesamiento de las rutas y el monitoreo, 
la gestión de los paquetes y el tracking dependen de los servidores regionales los cuales a su vez utilizan 
de forma directa la base de datos donde almacenan y consultan la información del sistema. 
Esto provoca un cuello de botella puesto que, la recepción de muchos pedidos por parte de un mismo punto provoca alta carga de consulta, alta latencia en la comunicación y problemas en la escalabilidad del sistema. La dependencia entre el servicio y la base de datos hace que cualquier retraso en la misma afecte a todo el funcionamiento de la plataforma y al uso de la misma para procesos como el tracking o las actualizaciones de estados.

**Solución**

Una propuesta de solución a los requerimientos es la posible utilización de una arquitectura de base de datos que además sea distribuida y escalable, 
en la que la información no dependa de un único punto central. Para ello, se podrían utilizar réplicas de la base de datos y particionamiento para la 
consulta se distribuye entre diferentes nodos, lo cual de esta manera intenta evitar la carga de un único servidor en particular. 
Además, también podemos incluir sistemas de caché y colas de mensajería de forma que podamos resolver las consultas de forma asíncrona y 
evitar que todos aquellos servicios consulten directamente a la base de datos al mismo tiempo.

3. **Dificultad para escalar globalmente**

El crecimiento de esta plataforma y su llegada a nuevas áreas o países implicará incluir más servidores de región para poder dar servicio al incremento de usuarios. 
Pero, en el ejemplo de arquitectura expuesto, estos nuevos servidores tendrían la dependencia del mismo sistema central. Es decir, se pueden añadir servidores para
comunicar el tráfico pero las solicitudes más importantes no harán sino ir hacia un único punto del sistema.

**Solución**

Una forma de resolver la situación mencionada sería desplegar una arquitectura multi-región con un verdadero estilo distribuido, 
de modo que cada zona geográfica cuente con su propia infraestructura parcial para la gestión de los servicios y los datos. 
En lugar de depender de una única infraestructura central, cada región contaría con instancias locales de los servicios críticos y 
las réplicas para la base de datos, 
siendo capaz dar salida a las peticiones de los usuarios en la región más cercana a estas.
