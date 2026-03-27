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
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE4MjM5MzE1OTEsLTE1ODg4NTUwMTEsMj
k4MTA3NTU1LDczMDc5MjU1MCwtMTM4MjM4MDIzOCwtMTM3NTIz
MDEwN119
-->