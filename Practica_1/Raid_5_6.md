Nombre:  Walter Vladimir Cantor Claros

Carnet: WC100218

## 1- Introducción

En esta práctica se implementaron arreglos RAID 5 y RAID 6 utilizando la herramienta mdadm en Linux, con el objetivo de analizar su eficiencia de almacenamiento, su nivel de tolerancia a fallos y el comportamiento del sistema durante procesos de reconstrucción (rebuild).

RAID (Redundant Array of Independent Disks) es una tecnología que permite combinar múltiples discos físicos en una unidad lógica para mejorar el rendimiento, la disponibilidad o la seguridad de los datos.

El RAID 5 utiliza paridad distribuida simple, lo que permite tolerar la falla de un disco sin pérdida de información. Por su parte, el RAID 6 implementa doble paridad distribuida, lo que incrementa la tolerancia a fallos permitiendo que dos discos fallen simultáneamente sin comprometer los datos.

En esta práctica se comparó el impacto de la paridad en la capacidad útil disponible, así como el comportamiento del sistema ante fallos simulados y procesos de reconstrucción automática.

**2. Configuración del Arreglo**

#### 2.1 RAID 5

**Discos utilizados:**  
/dev/nvme0n1  
/dev/nvme0n2  
/dev/nvme0n3  
/dev/nvme0n4  
/dev/nvme0n5

**Comando:**

sudo mdadm --create /dev/md5 --level=5 --raid-devices=5 \
/dev/nvme0n1 /dev/nvme0n2 /dev/nvme0n3 /dev/nvme0n4 /dev/nvme0n5

**Capacidad teorica esperada:**

(N - 1) discos  
(5 - 1) = 4 discos utiles

Si cada disco es de 5GB:  
4 x 5GB = 20GB utiles

**Capacidad real observada:**  

(Aproximadamente 20GB según salida de `df -h`)

#### 2.2 RAID 6
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk0OTg1NDAyNSwtMjA0NTE3NjAwNSwxMj
g1ODA1NTM1LC0yMDg4NzQ2NjEyXX0=
-->