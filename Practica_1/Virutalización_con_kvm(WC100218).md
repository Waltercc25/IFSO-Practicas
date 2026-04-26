# IFS0 - Practica 9

## Virtualización con KVM en Rocky Linux 10

## 1. Datos Generales

-   **Carrera:** Ingenieria en la Ciencia de la Computación.

-   **Asignatura:**  IFS0 - Analizando Necesidades de Infraestructura de Servidores

-   **Docente:** Elmer Elias Chanchan

-   **Unidad:**  3

-   **Practica:**  9 - Virtualizaci¢n con KVM

-   **Nombre del estudiante / integrantes:** Walter Vladimir Cantor Claros -- WC100218

# 2. Introducción

Describa brevemente el objetivo de la práctica y el contexto de virtualización con KVM.


# 3. Actividad 1 - Verificación del entorno y soporte de virtualización

## Resultados obtenidos

| Verificación | Resultado obtenido |
|---|---|
| Versión del kernel | Linux 6.12.0-124.49.1.el10_1.x86_64 |
| Flags vmx/svm presentes (cantidad) | 2 |
| Módulo kvm cargado | Sí |
| Módulo kvm_intel / kvm_amd cargado | Sí (kvm_amd) |
| Dispositivo /dev/kvm existe | Sí |
| systemd-detect-virt | oracle (VirtualBox) |

## Evidencia (actividad 1)


# 4. Actividad 2 - Instalación del stack KVM/QEMU/libvirt

## Resultados obtenidos

## Resultados obtenidos

| Verificación | Resultado obtenido |
|---|---|
| libvirtd activo (active/running) | Sí |
| virt-host-validate: KVM | PASS |
| virt-host-validate: QEMU | PASS |
| virsh list --all responde sin error | Sí |

## Evidencia

# 5. Actividad 3 - Preparación del almacenamiento y red virtual

## Resultados obtenidos

## Resultados obtenidos

| Verificación | Resultado obtenido |
|---|---|
| Pool default activo | Sí |
| Red default activa | Sí |
| Interfaz virbr0 presente | inet 192.168.122.1/24 |
| ISO Rocky Linux disponible en /var/lib/libvirt/images/ | Sí |

## Evidencia

# 6. Actividad 4 - Creación de máquina virtual

## Resultados obtenidos

| Parámetro de la VM | Valor observado |
|---|---|
| Nombre de la VM | vm-rocky10-lab |
| Estado | shut off |
| UUID | (resultado de virsh dominfo) |
| vCPUs asignadas | 1 |
| RAM asignada | 1024 MB |
| Disco virtual (ruta) | /var/lib/libvirt/images/vm-rocky10-lab.qcow2 |
| Tamaño del disco | 3 GB |
| Red asignada | default |






<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4NDQwMjIyNDAsMTgzNjc2MjUxMCwyMD
UzNjg3MDQyLC0xMDc3OTIwMDIxLC0yMDU3MTY3NjgxLC0xMDM2
NDgxMTcwLC0yMDg4NzQ2NjEyXX0=
-->