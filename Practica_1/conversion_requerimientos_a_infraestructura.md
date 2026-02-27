Nombre: Walter Vladimir Cantor Claros

Carnet: WC100218

Equipo: nomada-team-solo

## Conversión de Requerimientos a Infraestructura Física y Diseño Conceptual.

## Introducción al Escenario

La empresa analizada es una organización de servicios profesionales con 25 empleados que utiliza un sistema interno para gestionar documentos administrativos, información de clientes y proyectos.

El objetivo del análisis es transformar los requerimientos funcionales y no funcionales previamente validados en decisiones técnicas relacionadas con infraestructura física de servidores. Se busca definir roles de servidor y componentes físicos necesarios, justificando cada decisión desde una perspectiva conceptual sin realizar implementación ni seleccionar marcas o tecnologías específicas.

La propuesta debe garantizar disponibilidad durante la jornada laboral, acceso concurrente, protección de la información y capacidad de crecimiento gradual, minimizando riesgos técnicos como puntos únicos de falla (SPOF).

# Matriz de Conversión de Requerimientos

| Requerimiento                                 | Tipo (F/NF) | Atributo Técnico Derivado                           | Componente Físico Impactado | Decisión Conceptual                                          | Riesgo si no se implementa                         |
|----------------------------------------------|------------|----------------------------------------------------|-----------------------------|--------------------------------------------------------------|--------------------------------------------------|
| Acceso centralizado a la información          | F          | Servicio centralizado con almacenamiento compartido | Almacenamiento (RAID)       | Implementar arreglo RAID para tolerancia a fallos            | Pérdida total de información ante falla de disco |
| Acceso simultáneo de múltiples usuarios       | F          | Procesamiento concurrente                           | CPU / RAM                   | CPU con múltiples núcleos y RAM suficiente para concurrencia | Lentitud, bloqueos y baja productividad           |
| Disponibilidad en jornada laboral             | F          | Alta disponibilidad operativa                       | PSU / RAID                  | Fuente redundante y almacenamiento tolerante a fallos        | Interrupciones del servicio                       |
| Protección contra accesos no autorizados      | NF         | Segmentación y control de tráfico                   | NIC                         | Uso de múltiples interfaces de red para segmentación         | Exposición a accesos indebidos                    |
| Reducción de riesgo de pérdida de información | NF         | Redundancia de datos                                | RAID                        | RAID 1 o RAID 5 según criticidad                             | Pérdida irreversible de datos                     |
| Separación de componentes críticos            | NF         | Aislamiento lógico de servicios                     | CPU / RAM / NIC             | Separar roles en servidores distintos                        | Sobrecarga o fallo total del sistema              |
| Capacidad de crecimiento gradual              | NF         | Escalabilidad vertical y horizontal                 | RAM / Chasis / Expansión    | Chasis con ranuras libres y capacidad de ampliación          | Infraestructura obsoleta prematuramente           |


**Componentes que consideré:** CPU, RAM, RAID, NIC, PSU y Chasis/Expansión.

# Selección de Roles de Servidor

**Roles necesarios y justificación técnica de cada uno:**

| Rol de Servidor           | Requerimientos que atiende                                                          | Justificación Técnica                                                                                       |
|----------------------------|------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------|
| Servidor de Archivos       | Almacenamiento centralizado, acceso compartido, reducción de pérdida de información | Permite gestionar documentos administrativos con almacenamiento redundante y acceso concurrente controlado |
| Servidor de Base de Datos  | Registro y consulta de clientes y proyectos, acceso simultáneo                     | Separa la carga transaccional del almacenamiento documental, mejorando rendimiento y estabilidad           |
| Servidor de Aplicaciones   | Interfaz de acceso al sistema interno                                              | Aísla la lógica de negocio, evitando que una sobrecarga afecte directamente la base de datos               |

# Análisis físico por servidor:


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM5MTgyMTEyNywxMTQyNTIxMDQ0LDc4Nz
M1MTY4MywtMjg5NTcxMDcyLDEwMDQxNjIzMzIsLTE1NjY5NzQy
NjldfQ==
-->