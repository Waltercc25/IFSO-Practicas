
## Práctica 6 – Dimensionamiento Eléctrico, UPS y Densidad de Rack

## 1. Datos generales

 **Carrera:** Ingenieria en la ciencia de la computación.

**Asignatura:**  IFS0 – Analizando Necesidades de Infraestructura de Servidores.

**Nombre:** Walter Vladimir Cantor Claros.

**Carnet:** WC100218

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

I = 4,802 / 120

I = 40.01 A

Amperaje requerido = 40 A

## 8 Evaluación de capacidad del circuito

| Circuito | Capacidad segura | ¿Soporta la carga? |
|---|---|---|
| 15A | 1440 W | No |
| 20A | 1920 W | No |

La carga total estimada del rack es de **4,802 W**, la cual supera ampliamente la capacidad segura de los circuitos analizados.  
Un circuito de **15A** tiene una capacidad segura aproximada de **1440 W**, mientras que un circuito de **20A** soporta hasta **1920 W** considerando la regla del **80 % para cargas continuas**.

Debido a que **4,802 W > 1920 W**, ninguno de los dos circuitos puede alimentar la infraestructura de forma segura. Esto significa que, en un entorno real, sería necesario implementar **un circuito eléctrico dedicado de mayor capacidad o distribuir la carga entre varios circuitos**, además de utilizar **PDU y UPS adecuados para centros de datos**.

## 9 Estimación de autonomía del UPS

Porcentaje de carga = (Carga real / Capacidad UPS) × 100

**Resultado**

**UPS:**

4500 W capacidad

**Carga:**

4685 W

**Cálculo:**

**Porcentaje** = (4802 / 4500) × 100

**Porcentaje** = 106 %

## 10 Cálculo de carga térmica total

**Fórmula:**

BTU = W × 3.412

**Cálculo:**

4802 × 3.412 = 16384 BTU/h

**Resultado:**

Carga térmica total = 16,384 BTU/h

## 11 Densidad térmica del rack

| Equipo | U |
|---|---|
| Servidor aplicaciones | 2U |
| Servidor base datos | 2U |
| Servidor archivos | 4U |
| SAN | 2U |
| Switch | 1U |
| Firewall | 1U |
| UPS | 3U |
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTM2MDk0ODM5LC02NzQ5OTI3MTgsLTEzMT
E0ODM5MTQsLTE1NDkyOTUwODAsNzI5OTYzMTQxLC0xMDI0Mjk4
NDgyLC0xNzE5MDc4OTIsNzQ4NTQyODg5LC00Mzc5NjcxNTIsMT
g0ODkzNDc1NSwxMzI5MzQ3NDAwLDE2NjUwNTkwMDAsLTEwMTMw
MDI0NzYsLTEwMTIwOTI1NjQsMTAyOTAyMzgxMywxMDM3MjQ4OT
E0LDM0NzkwODM3OF19
-->