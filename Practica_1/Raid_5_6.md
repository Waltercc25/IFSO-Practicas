Nombre:  Walter Vladimir Cantor Claros

Carnet: WC100218

## Introducción

En esta práctica se implementaron arreglos RAID 5 y RAID 6 utilizando la herramienta mdadm en Linux, con el objetivo de analizar su eficiencia de almacenamiento, su nivel de tolerancia a fallos y el comportamiento del sistema durante procesos de reconstrucción (rebuild).

RAID (Redundant Array of Independent Disks) es una tecnología que permite combinar múltiples discos físicos en una unidad lógica para mejorar el rendimiento, la disponibilidad o la seguridad de los datos.

El RAID 5 utiliza paridad distribuida simple, lo que permite tolerar la falla de un disco sin pérdida de información. Por su parte, el RAID 6 implementa doble paridad distribuida, lo que incrementa la tolerancia a fallos permitiendo que dos discos fallen simultáneamente sin comprometer los datos.

En esta práctica se comparó el impacto de la paridad en la capacidad útil disponible, así como el comportamiento del sistema ante fallos simulados y procesos de reconstrucción automática.


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIwNDUxNzYwMDUsMTI4NTgwNTUzNSwtMj
A4ODc0NjYxMl19
-->