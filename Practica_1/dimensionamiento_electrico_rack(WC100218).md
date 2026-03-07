
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
| Servidor aplicaciones – HPE ProLiant DL380 Gen11 | 800 W | 2729 BTU/h | 2U | [HPE 800 W Flex Slot Platinum Hot-plug Low Halogen Power Supply  [HPE ProLiant DL380 Gen11 Server User Guide](https://support.hpe.com/hpesc/public/docDisplay?docId=sd00002446en_us&page=GUID-26120F6B-C550-4A8F-8200-0630EA6C4BE0.html) |
| Servidor base de datos – Dell PowerEdge R760 | 1000 W | 3412 BTU/h | 2U | [Dell PowerEdge R760 Technical Guide](https://www.delltechnologies.com/asset/en-au/products/servers/technical-support/poweredge-r760-technical-guide.pdf) |
| Servidor archivos – TrueNAS M50 | 975 W | 3327 BTU/h | 4U | [TrueNAS M50 Storage Data Sheet](https://www.itcreations.com/user-manuals/m50-manuals/truenas-m50-storage-data-sheet.pdf?srsltid=AfmBOoqEto9NVhIc70FH3OYlcthtj191J8ioSTs4zpbLe7BRIHbxMy-v) |
| Switch – Cisco Catalyst 9300-48P | 715 W | 2440 BTU/h | 1U | [Catalyst 9300 Series Switches Data Sheet - Cisco](https://www.cisco.com/c/en/us/products/collateral/switches/catalyst-9300-series-switches/nb-06-cat9300-ser-data-sheet-cte-en.html) |
| Firewall – FortiGate 100F | 40 W | 122 BTU/h | 1U | [FortiGate 100F Series Data Sheet](https://www.fortinet.com/content/dam/fortinet/assets/data-sheets/pdf/fortigate-100f-series.pdf) |
| SAN – Dell PowerStore 1200T | 1272 W | 4094 BTU/h | 2U | [PowerStore 1200T All-Flash Storage  Dell Ireland](https://www.dell.com/en-ie/shop/ipovw/powerstore-1200t) |

## 5 Selección del UPS

| Característica | Valor |
|---|---|
| Modelo seleccionado | APC Smart-UPS SRT 5000VA (SRT5KRMXLT) |
| Capacidad VA | 5000 VA |
| Capacidad W | 4500 W |
| Eficiencia | 94 % |
| Disipación térmica | 1047 BTU/h |
| Tamaño rack | 3U |
| Autonomía nominal aproximada | 3 a 5 minutos a plena carga (4250W-4800W)  y cerca de  12 a 15 minutos a media carga (2100W-2400W) |
| Fuente | [UPS-SRT5KRMXLT-IEC_DATA SHEET.PDF](https://iportal2.schneider-electric.com/Contents/docs/UPS-SRT5KRMXLT-IEC_DATA%20SHEET.PDF) |

## 6 Cálculo de carga eléctrica total

Realice el cálculo del consumo eléctrico total de la infraestructura.

Servidor aplicaciones = 800 W

Servidor base datos = 1000 W

Servidor archivos = 975 W

Switch = 715 W

Firewall = 40 W

SAN = 1272 W

Potencia total = 800 + 1000 + 975 + 715 + 40 + 1272

**Potencia total = 4,802 W**

## 7 Cálculo de amperaje del circuito

Utilice la fórmula:

I = P / V

Donde:

-   **I**  = Corriente (A)
-   **P**  = Potencia (W)
-   **V**  = Voltaje (V)

Considere una alimentación de  **120V**.

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTc1MzM3NTQwOCwtMTAyNDI5ODQ4MiwtMT
cxOTA3ODkyLDc0ODU0Mjg4OSwtNDM3OTY3MTUyLDE4NDg5MzQ3
NTUsMTMyOTM0NzQwMCwxNjY1MDU5MDAwLC0xMDEzMDAyNDc2LC
0xMDEyMDkyNTY0LDEwMjkwMjM4MTMsMTAzNzI0ODkxNCwzNDc5
MDgzNzhdfQ==
-->