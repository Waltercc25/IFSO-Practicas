# IFS0 - Practica 10

## Administración y Monitoreo de Máquinas Virtuales KVM
----------

## 1. Datos generales

-   **Carrera:** 

-   **Asignatura:**  IFS0 - Analizando Necesidades de Infraestructura de Servidores

-   **Docente:**

-   **Unidad:**  3

-   **Pr ctica:**  10 - Administraci¢n KVM

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

## 4. Actividad 2 - Snapshots con virsh
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTM3MTk4NTQwNiwtMjEyNDAzMDg2OSwtMT
Q3MTYwMzA1Nl19
-->