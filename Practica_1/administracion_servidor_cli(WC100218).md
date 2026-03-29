# IFS0 – Práctica 8

## Administración de Servidores Linux mediante CLI

## 1. Datos generales

-   **Asignatura:**  IFS0 – Analizando Necesidades de Infraestructura de Servidores

-   **Periodo:**  3

-   **Práctica:**  8 – Administración de Servidores Linux

-   **Nombre:**  Walter Vladimir Cantor Claros - WC100218

## 2. Introducción

En este documento se presenta el análisis del estado de un servidor Linux utilizando herramientas de línea de comandos (CLI).

El objetivo es evaluar el comportamiento del sistema en términos de:

-   uso de CPU
-   uso de memoria
-   almacenamiento
-   red
-   servicios
-   usuarios

y demostrar la capacidad de interpretar métricas para la toma de decisiones técnicas.

## 3. Información del sistema

### Comandos ejecutados

uname -a

hostnamectl

uptime

## Resultados

## Análisis

-   **Versión del sistema operativo:** Ubuntu 22.04.5 LTS

-   **Arquitectura:** x86-64

-   **Tiempo de actividad:** up 2 min

-   **Load average:** 0.39, 0.28, 0.11

**Interpretación técnica:**

Los comandos `uname -a`, `hostnamectl` y `uptime` permiten obtener una visión general del estado del sistema.

-   A través de `uname -a` y `hostnamectl`, se identifica la versión del sistema operativo y la arquitectura del servidor, lo cual es fundamental para verificar compatibilidad de software y actualizaciones.
-   El comando `uptime` permite evaluar el tiempo de actividad del servidor y la carga promedio (_load average_) en intervalos de 1, 5 y 15 minutos.

Un sistema se considera estable cuando el _load average_ es igual o menor al número de núcleos del procesador, lo que indica que los procesos están siendo atendidos sin sobrecarga.

## 4. Análisis de CPU y procesos

## Comandos ejecutados

top

ps aux

ps aux --sort=-%cpu | head

## Resultados

## Análisis

-   **Proceso con mayor uso de CPU:** MYSQL

-   **% de CPU utilizado:** 6.2

**Interpretación técnica:**

-   **¿Existe sobrecarga del sistema?** según la imagen tomada de los procesos, no existe ninguna sobrecarga en el sistema ya que la CPU no esta siendo forzada por encima del 80% de uso y se refleja un uso normal

-   **¿Qué podría causar ese consumo?** Mysql es un servicio que tiene que estar corriendo para poder hacer uso de base de datos en el sistema pero no causa major consumo de CPU así que lo consideramos dentro de un buen rango.

## 5. Análisis de memoria

### Comandos ejecutados

free -h

vmstat 1

## Resultados


## Análisis

-   **Memoria total:** 7.0 Gi
    
-   **Memoria usada:** 586 Mi
    
-   **Memoria libre:** 6.0 Gi
    
-   **Uso de swap:** 0B

**Interpretación técnica:**

-   **¿El uso de memoria es adecuado?** El uso de memoria es adecuado ya que no se ha usado bastante el dispositivo y concuerda con todo lo que he descargado.
    
-   **¿Existe uso de swap? ¿Qué implica?** tengo un uso de 0B y El uso de swap en 0B indica que la memoria RAM disponible es suficiente para soportar la carga actual del sistema, por lo que no es necesario recurrir a memoria virtual en disco.

## 6. Análisis de almacenamiento

### Comandos ejecutados

df -h

du -sh /var/log

lsblk

## Resultados


## Análisis

-   **Partición con mayor uso:** a partición **con mayor uso real es** `ubuntu--vg-ubuntu--lv` **(11.5G en** `/`**)**, porque es la que contiene el sistema operativo y donde se almacenan la mayoría de los datos.
    
-   **Directorios con mayor consumo:** ubuntu--vg-ubuntu--lv con 53% en uso.
    

**Interpretación técnica:**

-   **¿Existe riesgo de saturación?** aparentemente no existe riesgo ya que se tiene suficiente espacio no solamente en esa parte del disco si no que en el raid 5 que esta instalado 
    
-   **¿Qué acciones recomendaría?** limpiar o se pudiera distribuir la carga con los otros discos.

## 7. Análisis de red

### Comandos ejecutados

ip a

ping 8.8.8.8

ss -tuln

## Resultados

## Análisis


-   Dirección IP del servidor:
    
-   Conectividad:
    
-   Puertos abiertos:
    

**Interpretación técnica:**

-   ¿El servidor está accesible?, Sí, el servidor esta accesible, ya que con el comando de ping 8.8.8.8 tuvimos acceso a internet sin perdida de paquetes.
    
-   ¿Hay servicios expuestos?, Sí, hay servicios expuestos que están en estado LISTEN por ejemplo: 
-    `127.0.0.1:3306` (MySQL local)

-   `127.0.0.53:53` (DNS local)

## 8. Gestión de servicios

### Comandos ejecutados

systemctl status ssh

systemctl restart ssh

systemctl enable ssh


### Resultados

## Análisis

-   **Estado del servicio:** Activo (Running)
    
-   **Acción realizada:** se verifico el estado del servidor SSH y se hizo un reseteo del servicio de SSH pero luego de eso se hizo el activo permanente del servicio para acceso remoto permanente.
    

**Interpretación técnica:**

-   **¿Por qué es crítico este servicio?** es crítico ya que nos permite activar el servidor SSH que es el que nos ayuda a que otros se conecten al servidor de forma remota y que tenemos instalado para poder trabajar en el.
    
-   **¿Qué impacto tendría su falla?** si llegara a fallar, el servidor quedaría inaccesible para que otros usuarios se conecten de forma remota y no poder administrarlo. 


## 9. Gestión de usuarios y permisos

### Comandos ejecutados

who

useradd usuario_prueba

passwd usuario_prueba

chmod 755 archivo.txt

### Resultados

## Análisis

-   **Usuario creado:** usuario_prueba
    
-   **Permisos asignados:** tiene permisos de dueño leer, escribir y ejecutar y eso significa que el dueño puede ejecutar esas 3 acciones y los otros solo pueden leer y ejecutar.

**Interpretación técnica:**

-   ¿Qué implica el permiso 755?

     **`chmod 755` significa:**

-   Dueño → puede **leer, escribir y ejecutar**

-   Grupo → puede **leer y ejecutar**

-   Otros → pueden **leer y ejecutar**
    
-   **¿Qué riesgos existen con permisos incorrectos?** existe manipulación incorrecta de los datos en los servidores o en los archivos que necesitan cierta restricción por ejemplo un riesgo es asignar 777 en permisos

## 10. Automatización con Bash

### Script desarrollado

#!/bin/bash

echo "Estado del sistema:"
uptime

echo "Uso de memoria:"
free -h

echo "Uso de disco:"
df -h

## Explicación del script

-   **¿Qué hace el script?** lo que hace es crear un script que se ejecutar con Bash de forma automática cuando lo llamamos y lo usamos, entre las cosas que hacer es mostrar el estado del sistema y la carga con (uptime) muestra el uso de memoria RAM (free -h) y (df -h) que muestra el uso del disco

-   **¿Qué comandos utiliza?** uptime, free -h, df -h

### Resultado de ejecución

### Mejora propuesta

El script puede mejorarse significativamente para su uso en un entorno de producción mediante la incorporación de funcionalidades adicionales que permitan un monitoreo más completo y automatizado del sistema.

Entre las principales mejoras se incluyen:

-   **Registro de información en archivos (logs):**  
    Guardar la salida del script en un archivo `.log` permite llevar un historial del estado del sistema para auditorías y análisis posteriores.
    
-   **Automatización con tareas programadas (cron):**  
    Ejecutar el script de forma periódica permite monitorear continuamente el servidor sin intervención manual.
    
-   **Validación de errores:**  
    Implementar controles para detectar fallos en la ejecución de comandos y evitar resultados incompletos o incorrectos.
    
-   **Alertas automáticas:**  
    Enviar notificaciones (por ejemplo, por correo) cuando el uso de CPU, memoria o disco supere ciertos límites críticos.
    
-   **Mayor detalle en la información:**  
    Incluir más comandos como `top`, `ps aux` o `ss -tuln` para obtener un análisis más completo del sistema.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk3MTY3NTU3MiwxMjk2NjQ0Mzg4LDE1Mj
U5OTM1OTUsNzg4Nzk4NTE3LC0xNjY0ODM2NzMsLTE0NTU5NjA4
NTQsNzI4MTMxNDU2LDEzNDkyMTMyOTgsMTAyNzcwNzU0NSwtMT
Y3MDM0NDE3MSwxNzIzMDU2NzgsLTE1ODg4NTUwMTEsMjk4MTA3
NTU1LDczMDc5MjU1MCwtMTM4MjM4MDIzOCwtMTM3NTIzMDEwN1
19
-->