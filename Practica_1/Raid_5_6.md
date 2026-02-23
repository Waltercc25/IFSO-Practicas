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

**Discos utilizados:**  

/dev/nvme0n6  
/dev/nvme0n7  
/dev/nvme0n8  
/dev/nvme0n9  
/dev/nvme0n10

 **Comando:**

sudo mdadm --create /dev/md6 --level=6 --raid-devices=5 \
/dev/nvme0n6 /dev/nvme0n7 /dev/nvme0n8 /dev/nvme0n9 /dev/nvme0n10

**Capacidad teórica esperada:**

(N - 2) discos  
(5 - 2) = 3 discos utiles

Si cada disco es de 5GB:  
3 x 5GB = 15GB utiles

**Capacidad real observada:**

(Aproximadamente 15GB según salida de `df -h`)

## 3. Analisis de Espacio

Salida de:

df -h


**Tabla comparativa:**


| RAID   | Discos | Capacidad útil | Pérdida por paridad |
|--------|--------|---------------|---------------------|
| RAID 5 | 5      | ~20 GB        | 1 disco             |
| RAID 6 | 5      | ~15 GB        | 2 discos            |

**Explicación de resultados:**

Se observa que RAID 5 ofrece mayor capacidad util debido a que solo sacrifica un disco para paridad. RAID 6 sacrifica dos discos para doble paridad, reduciendo el espacio disponible, pero aumentando significativamente la tolerancia a fallos.

## 4. Simulacion de Fallos

#### 4.1 RAID 5 - 1 fallo

**Disco fallado:**

/dev/nvme0n1

**Estado del arreglo:**

El arreglo pasó a estado degradado pero permaneció operativo.

 **Evidencia de persistencia de datos:**
 
El archivo fue accesible incluso después de simular la falla:
 
 cat /mnt/raid5/seguridad.txt

#### 4.2 RAID 6 - 2 fallos

   **Discos fallados:**

/dev/nvme0n6  
/dev/nvme0n7

**Estado:**

El arreglo permaneció funcional a pesar de dos fallos simultaneos.

**Evidencia:**

Los datos permanecieron accesibles:

cat /mnt/raid6/seguridad.txt

## 5. Reconstrucción

**Salida relevante de:**

cat /proc/mdstat

## 6. Comparacion Tecnica

**Diferencia en seguridad:**  
RAID 6 ofrece mayor seguridad al tolerar dos fallos simultaneos, mientras que RAID 5 solo tolera uno.

**Diferencia en rendimiento:**  
RAID 5 tiene mejor rendimiento en escritura comparado con RAID 6 debido a que solo calcula una paridad.

Impacto del doble calculo de paridad:  
En RAID 6 se realizan dos calculos de paridad, lo que aumenta la carga del sistema y reduce ligeramente el rendimiento de escritura.

¿Cual usaria para almacenamiento critico?  
Para almacenamiento critico se recomienda RAID 6 debido a su mayor tolerancia a fallos y seguridad ante fallas multiples.


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTc5MjUwNzQ2OCw1MTEyNTIxODIsMjEzMD
g1ODg1MywtMjA0NTE3NjAwNSwxMjg1ODA1NTM1LC0yMDg4NzQ2
NjEyXX0=
-->