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

## Evidencia

# 7. Análisis técnico

## 7. Análisis técnico

- ¿El host soporta virtualización correctamente?

Sí, el host soporta virtualización correctamente. Se verificó la presencia
de las extensiones de virtualización (svm en CPU AMD) y la disponibilidad
del dispositivo /dev/kvm. Asimismo, los módulos kvm y kvm_amd se encuentran
cargados en el sistema, lo que confirma que el hardware es compatible con KVM.

- ¿El stack KVM está funcionando sin errores?

El stack de virtualización (KVM, QEMU y libvirt) se encuentra correctamente
instalado y funcional. La herramienta virt-host-validate mostró resultados
satisfactorios (PASS y WARN), sin errores críticos. Las advertencias observadas
son normales en entornos virtualizados sobre VirtualBox y no afectan el
funcionamiento general del sistema.

- ¿La VM fue creada correctamente?

Sí, la máquina virtual fue creada correctamente utilizando virt-install.
Se asignaron recursos de CPU, memoria y almacenamiento desde el pool default,
y se configuró la red virtual NAT. Aunque se presentó un error "Guru Meditation"
al intentar ejecutarla, este corresponde a una limitación del entorno de
virtualización anidada en VirtualBox y no a un fallo en la configuración
de la VM.

- ¿Qué ventajas observa al usar KVM en este entorno?

El uso de KVM permite aprovechar las capacidades de virtualización del hardware,
ofreciendo alto rendimiento y eficiencia en comparación con soluciones de
virtualización puramente por software. Además, KVM se integra con herramientas
como libvirt, facilitando la administración mediante CLI. Permite crear,
gestionar y automatizar máquinas virtuales, optimizando el uso de recursos
del servidor y mejorando la escalabilidad de la infraestructura.


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTk0Mjk1NzcyOSwtMjIyNTAwODAzLC0xOD
Q0MDIyMjQwLDE4MzY3NjI1MTAsMjA1MzY4NzA0MiwtMTA3Nzky
MDAyMSwtMjA1NzE2NzY4MSwtMTAzNjQ4MTE3MCwtMjA4ODc0Nj
YxMl19
-->