**IFS0 – Práctica 7**

**Diseño de Rack de Servidores Basado en Normativas**

## 1. Datos generales

-   **Carrera:** Ingeniería en la ciencias de la computación.
    
-   **Asignatura:** IFS0 – Analizando Necesidades de Infraestructura de Servidores

**Nombre del estudiante / integrantes:** 

Walter Vladimir Cantor Claros -> WC100218

## 2. Introducción

[](https://github.com/echanchanclass/practica-7-normativas-de-centros-de-datos-nomada-team-solo/blob/master/practica_7/diseno_rack_normativas.md#2-introducci%C3%B3n)

En este documento se presenta el diseño físico de un rack de servidores de  **42U**, elaborado a partir de la investigación de  **normativas y buenas prácticas de centros de datos**.

El objetivo de esta práctica es diseñar una distribución adecuada de equipos de infraestructura considerando:

-   organización del rack
-   gestión de energía
-   flujo de aire
-   gestión de cableado
-   estándares de centros de datos

El diseño fue modelado utilizando la herramienta  **Rackula**.

## 3. Normativas investigadas

Investigue al menos  **tres estándares utilizados en el diseño de centros de datos**.

| Estándar     | Organización                            | Área que regula                         | Aplicación en racks |
|--------------|-----------------------------------------|-----------------------------------------|---------------------|
| ANSI/TIA-942 | Telecommunications Industry Association | Infraestructura de centros de datos     | Define buenas prácticas para distribución de racks, cableado estructurado, redundancia eléctrica, flujo de aire y organización de equipos en centros de datos. |
| EIA-310-E    | Electronic Industries Alliance          | Estándar físico de racks de 19 pulgadas | Define dimensiones físicas de racks y equipos (ancho, altura en U, montaje), garantizando compatibilidad entre servidores, switches, UPS y demás dispositivos instalados en racks. |
| TIA-606-C    | Telecommunications Industry Association | Administración y etiquetado de cableado | Establece normas para la correcta identificación, etiquetado y documentación del cableado dentro del rack, facilitando mantenimiento y gestión de infraestructura. |

## 4. Análisis del hardware

Investigue las características físicas de los equipos utilizados en la práctica.

| Equipo | Altura (U) | Tipo | Consumo aproximado | Función |
|------|------|------|------|------|
| Servidor de aplicaciones | 2U | Servidor rack | ~800 W | Ejecuta aplicaciones empresariales utilizadas por los usuarios de la organización. |
| Servidor de base de datos | 2U | Servidor rack | ~900 W | Almacena y gestiona bases de datos críticas para los sistemas de la empresa. |
| Servidor de archivos | 4U | Servidor de almacenamiento | ~1200 W | Proporciona almacenamiento centralizado para archivos compartidos en la red. |
| SAN | 2U | Almacenamiento empresarial | ~1000 W | Sistema de almacenamiento de alto rendimiento utilizado para servidores y virtualización. |
| Switch | 1U | Equipo de red | ~350 W | Conecta todos los dispositivos del rack a la red empresarial. |
| Firewall | 1U | Seguridad de red | ~150 W | Protege la red interna mediante filtrado de tráfico y políticas de seguridad. |
| UPS | 6U | Sistema de energía | ~6000 W capacidad | Proporciona energía de respaldo y protección eléctrica ante fallos de suministro. |


## 5. Diseño del rack

El diseño del rack fue realizado siguiendo buenas prácticas de infraestructura de centros de datos y considerando estabilidad mecánica, flujo de aire, distribución eléctrica y organización del cableado.

La distribución de los equipos se organizó por capas funcionales dentro del rack.

En la **parte inferior del rack** se colocó el **UPS Smart-UPS SRT5KRMXLT**, ya que es uno de los equipos más pesados. Colocar el UPS en la base mejora la estabilidad del rack y reduce el riesgo de desequilibrio estructural.

Encima del UPS se ubicó el **sistema de almacenamiento (Storage / SAN)**. Esta posición permite mantener cercanía con los servidores que utilizan el almacenamiento, reduciendo la longitud de cables y mejorando la organización del cableado.

En la **zona media del rack** se instalaron los **servidores**:

- HPE ProLiant DL380 Gen11 (Servidor de aplicaciones)
- Dell PowerEdge R760 (Servidor de base de datos)
- Servidor de archivos

Ubicar los servidores en la parte media del rack permite mantener un equilibrio térmico y facilita el acceso para mantenimiento.

En la **parte superior del rack** se instalaron los equipos de red:

- Switch de red (48 puertos)
- Router / Firewall

Esto se realiza comúnmente en centros de datos porque facilita la distribución del cableado de red hacia otros racks o hacia los patch panels de la infraestructura.

Además, se dejaron **espacios libres entre algunos equipos**, los cuales pueden ser utilizados para instalar **blank panels o cable managers**, lo que ayuda a mejorar el flujo de aire y la organización del cableado.

Este diseño sigue el principio de organización típico de centros de datos:

- energía en la parte inferior
- almacenamiento y servidores en la zona media
- red en la parte superior

## 6. Gestión térmica del rack


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4Mjc5MDA4ODYsLTUxOTI5NTUxNiwtMT
c0NDY0ODQ2NSwzMDUxOTg0MjcsLTIwMTk2NTA4MDAsLTIwMzUy
OTk0OTksLTQzNTg3NjY1NywtMjAwNjg5MDIwOCwtMjA4OTgwMj
Q1LC0xOTYyODY4MTcyLC0yMDg4NzQ2NjEyXX0=
-->