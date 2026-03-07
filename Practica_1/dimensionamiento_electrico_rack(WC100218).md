
## Práctica 6 – Dimensionamiento Eléctrico, UPS y Densidad de Rack

## 1. Datos generales

 **Carrera:** Ingenieria en la ciencia de la computación.

**Asignatura:**  IFS0 – Analizando Necesidades de Infraestructura de Servidores.

**Nombre:** Walter Vladimir Cantor Claros.

**Aquipo:** Nomada-team-solo.

## 2 Introducción

En este documento se presenta el análisis eléctrico y térmico de una infraestructura de servidores instalada en un rack estándar de centro de datos.

El objetivo de la práctica es calcular el consumo eléctrico total de la infraestructura, evaluar la capacidad del circuito eléctrico, estimar la autonomía del sistema de respaldo UPS y analizar la densidad térmica generada dentro del rack.

Este análisis permite comprender cómo el diseño eléctrico y térmico influye en la disponibilidad y estabilidad de los servicios de infraestructura.

## 3 Equipos analizados

| Equipo | Modelo |
|------|------|
| Servidor de aplicaciones | HPE ProLiant DL380 Gen11 |
| Servidor de base de datos | Dell PowerEdge R760 |
| Servidor de archivos | TrueNAS M50 Enterprise |
| Switch de red | Cisco Catalyst 9300-48P |
| Firewall | FortiGate 100F |
| Almacenamiento SAN | Dell PowerStore 1200T |

## 4 Investigación de especificaciones técnicas

Complete la siguiente tabla con las especificaciones investigadas.

| Equipo | Potencia Máxima (W) | BTU/h | Tamaño (U) | Fuente |
|---|---|---|---|---|
| Servidor aplicaciones – HPE ProLiant DL380 Gen11 | 800 W | 2729 BTU/h | 2U | [HPE 800 W Flex Slot Platinum Hot-plug Low Halogen Power Supply | HPE ProLiant DL380 Gen11 Server User Guide](https://support.hpe.com/hpesc/public/docDisplay?docId=sd00002446en_us&page=GUID-26120F6B-C550-4A8F-8200-0630EA6C4BE0.html) |
| Servidor base de datos – Dell PowerEdge R760 | 1000 W | 3412 BTU/h | 2U | Dell Technical Guide |
| Servidor archivos – TrueNAS M50 | 900 W | 3070 BTU/h | 4U | iXsystems Documentation |
| Switch – Cisco Catalyst 9300-48P | 715 W | 2440 BTU/h | 1U | Cisco Datasheet |
| Firewall – FortiGate 100F | 70 W | 239 BTU/h | 1U | Fortinet Datasheet |
| SAN – Dell PowerStore 1200T | 1200 W | 4094 BTU/h | 2U | Dell PowerStore Docs |
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTAyOTAyMzgxMywxMDM3MjQ4OTE0LDM0Nz
kwODM3OF19
-->