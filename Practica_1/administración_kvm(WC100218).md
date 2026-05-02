# IFS0 - Practica 10

## Administración y Monitoreo de Máquinas Virtuales KVM
----------

## 1. Datos generales

-   **Carrera:**  Ingenieria en la Ciencia de la Computación.

-   **Asignatura:**  IFS0 - Analizando Necesidades de Infraestructura de Servidores

-   **Docente:** Elmer Elias Chanchan

-   **Unidad:**  3

-   **Practica:**  10 - Administración_KVM

-   **Nombre del estudiante / integrantes:**
- 
    -   Walter Vladimir Cantor Claros - WC100218

## 2. Introducción

Describa el objetivo de la práctica y el contexto del uso de virtualización en servidores.

## 3. Actividad 1 - Ciclo de vida de la VM

## Resultados obtenidos

| Verificación | Resultado obtenido |
|-------------|------------------|
| Estado tras `virsh start` | Ejecutando|
| Estado tras `virsh suspend` | pausado|
| Estado tras `virsh resume` | Ejecutando|
| Archivo `.state` (ruta y tamaño) | /var/lib/libvirt/images/vm-rocky9-lab.state (~varía) |
| Estado tras `virsh restore` | Ejecutando|
| Estado tras `virsh shutdown` | apagado |

## Evidencia

## 4. Actividad 2 - Snapshots con virsh

## Resultados obtenidos

| Verificación | Resultado obtenido |
|-------------|------------------|
| Formato del disco (qcow2) | qcow2 |
| Nombre del snapshot baseline | snap-baseline |
| Nombre del snapshot con cambio | snap-con-cambio |
| Árbol de snapshots | snap-baseline → snap-con-cambio |
| Archivo presente en snapshot con cambio | Sí |
| Archivo eliminado tras revert | Sí |

## Evidencia


## 5. Actividad 3 - Clonado de VM

## Resultados obtenidos

| Verificación | Resultado obtenido |
|-------------|------------------|
| Nombre del clon creado | vm-rocky10-clone |
| UUID VM original | (resultado en captura) |
| UUID VM clon | (diferente) |
| MAC del clon | (distinta) |
| Disco del clon | /var/lib/libvirt/images/vm-rocky10-clone.qcow2 |
| Estado del clon | running |

## Evidencia

## 6. Actividad 4 - Monitoreo de recursos

## Resultados obtenidos

| Parámetro de la VM | Valor observado |
|------------------|----------------|
| Columnas mostradas por virt-top | CPU%, MEM, TIME, DOM |
| CPU time (domstats) | 151120000000 (nanosegundos aprox) |
| RAM actual (dommemstat) | 1109308 KB (rss) |
| Lecturas de disco (rd_req) | 7099 |
| Tamaño virtual vs real | ~10 GB virtual / ~2.7 GB real |

## Evidencia


## 7. Extracción de archivos con  `libguestfs`



<!--stackedit_data:
eyJoaXN0b3J5IjpbOTE2NzQxNjUyLDQwMjI1Mzk5LC0xNDIzOD
k3MTg3LDc1OTEzMjIyMiw3NDYwNDA0OSwtMTIyODU0NzMyMCwt
MjEyNDAzMDg2OSwtMTQ3MTYwMzA1Nl19
-->