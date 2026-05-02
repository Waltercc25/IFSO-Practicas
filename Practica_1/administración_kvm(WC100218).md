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


## Resultados

| Acción | Resultado |
|--------|----------|
| Sistemas detectados | No ejecutado por limitación de VirtualBox |
| Uso de disco (virt-df) | No ejecutado por limitación de VirtualBox |
| Archivo extraído (/etc/hostname) | No ejecutado |

## 8. Análisis técnico

- ¿Qué ventajas ofrece el uso de snapshots en producción?

Los snapshots permiten capturar el estado completo de una máquina virtual en un momento específico, incluyendo disco y, en algunos casos, memoria. En entornos de producción, esto facilita la recuperación rápida ante fallos, errores de configuración o actualizaciones fallidas. Además, permiten realizar pruebas de cambios críticos con la posibilidad de revertir al estado anterior en segundos, reduciendo significativamente el riesgo operativo y el tiempo de inactividad.

- ¿Por qué el clonado es importante en entornos empresariales?

El clonado permite replicar máquinas virtuales completas de manera rápida y eficiente, generando nuevas instancias con configuraciones idénticas sin necesidad de reinstalar el sistema operativo. Esto es fundamental en entornos empresariales para el aprovisionamiento rápido de servidores, despliegue de servicios escalables, creación de entornos de pruebas y recuperación ante desastres. También es la base de metodologías modernas como infraestructura como código (IaC).

- ¿Qué riesgos existen si no se monitorean las VMs?

La falta de monitoreo puede generar múltiples problemas críticos, como sobrecarga de CPU, uso excesivo de memoria, saturación de disco o fallos en la red, los cuales pueden pasar desapercibidos hasta causar caídas del sistema. Además, sin monitoreo no es posible anticipar problemas de rendimiento, detectar cuellos de botella ni optimizar recursos, lo que afecta la disponibilidad y confiabilidad de los servicios. En entornos productivos, esto puede traducirse en pérdida de datos o interrupción de servicios.

- ¿Cómo contribuye KVM a la alta disponibilidad (HA)?

KVM contribuye a la alta disponibilidad al permitir la virtualización eficiente de múltiples sistemas en un mismo host, facilitando la migración, clonación y recuperación de máquinas virtuales. Al integrarse con herramientas como libvirt, permite automatizar operaciones del ciclo de vida de las VMs, reduciendo tiempos de recuperación ante fallos. Además, su compatibilidad con soluciones de clustering y balanceo de carga permite distribuir servicios y mantenerlos operativos incluso ante fallas de hardware.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3MDA1NDczMTYsNjUwMDI3Mjg1LDkxNj
c0MTY1Miw0MDIyNTM5OSwtMTQyMzg5NzE4Nyw3NTkxMzIyMjIs
NzQ2MDQwNDksLTEyMjg1NDczMjAsLTIxMjQwMzA4NjksLTE0Nz
E2MDMwNTZdfQ==
-->