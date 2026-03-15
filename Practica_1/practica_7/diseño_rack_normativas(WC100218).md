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

Explique cómo organizó los equipos dentro del rack.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3NDQ2NDg0NjUsMzA1MTk4NDI3LC0yMD
E5NjUwODAwLC0yMDM1Mjk5NDk5LC00MzU4NzY2NTcsLTIwMDY4
OTAyMDgsLTIwODk4MDI0NSwtMTk2Mjg2ODE3MiwtMjA4ODc0Nj
YxMl19
-->