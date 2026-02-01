**Nombre**: Walter Vladimir Cantor Claros. -> WC100218

**Trabajo**: - Practica_2 - Individual

 **2. INTRODUCCIÓN DEL CASO**

Una  **empresa comercial pequeña**, con  **20 empleados**, utiliza un sistema interno para:

-   Almacenar documentos administrativos
-   Compartir archivos entre áreas
-   Registrar información básica de clientes

Actualmente la empresa presenta los siguientes problemas:

-   El sistema se vuelve lento cuando varios usuarios trabajan al mismo tiempo
-   Algunos documentos desaparecen o se sobrescriben
-   El sistema deja de funcionar de forma inesperada durante la jornada laboral

La empresa:

-   No cuenta con documentación técnica
-   No tiene personal especializado en TI
-   Describe los problemas £nicamente desde su experiencia diaria

**3. REQUERIMIENTOS SELECCIONADOS:**

**R1**. El sistema debe permitir que varios usuarios trabajen al mismo tiempo sin volverse lento.

**Origen (necesidad):**
Necesidad operativa implícita.
Surge de la experiencia diaria de los empleados al usar el sistema de forma simultánea y notar lentitud que afecta su productividad, aunque no se expresa en términos técnicos.

**R2**. El sistema debe garantizar que los documentos no se pierdan ni se sobrescriban accidentalmente.

**Origen (necesidad):**
Necesidad operativa explícita.
Se origina a partir de la pérdida real de documentos y sobreescrituras ocurridas varias veces, lo cual fue claramente identificado y expresado por los usuarios.

**R3**. El sistema debe estar disponible y no fallar de forma inesperada durante la jornada laboral.

**Origen (necesidad):**
Necesidad operativa explícita.
Proviene de las fallas frecuentes del sistema que interrumpen completamente las actividades laborales, siendo un problema reconocido directamente por los usuarios.

**4. VALIDACIÓN DE REQUERIMIENTOS:**

**4.1 - Tipo de instrumento:** Entrevista.

-   **Justificación de la elección:** elegí la entrevista ya que siento que puedes hacer preguntas un poco más concretas para descartar cosas que pueden ser o no ser las causas del problema.

**4.2 - PREGUNTAS UTILIZADAS:**

1- ¿Con qué frecuencia nota que el sistema se vuelve lento cuando varios empleados lo usan al mismo tiempo? **R// Frecuentemente**

2- Cuando el sistema se vuelve lento, ¿afecta su trabajo diario o retrasa sus actividades? **R// bastante**

3- ¿Ha experimentado pérdida de documentos o que un archivo haya sido reemplazado por otro sin intención? **R// varias veces**

4- ¿Qué tan importante es para usted que los documentos almacenados se mantengan seguros y sin cambios no autorizados? R// **muy importante**

5- ¿Ha ocurrido que el sistema deje de funcionar durante su jornada laboral impidiéndole continuar su trabajo? **R// Frecuentemente**

**4.3 RESULTADO DE VALIDACIÓN:** 

| Requerimiento | ¿Es correcto? | ¿Es necesario? | ¿Es comprensible para el usuario? |
|--------------|---------------|----------------|-----------------------------------|
| R1           | Sí            | Sí             | Sí                                |
| R2           | Sí            | Sí             | Sí                                |
| R3           | Sí            | Sí             | Sí                                |


**5. PRIORIZACIÓN DE REQUERIMIENTOS (MATRIZ).**


| Requerimiento | Impacto operativo | Criticidad técnica | Prioridad |
| ------------- | ----------------- | ------------------ | --------- |
| R1            | Alto              | Medio              | Media     |
| R2            | Alto              | Alto               | Alta      |
| R3            | Muy alto          | Alto               | Alta      |

**5.2 - JUSTIFICACIÓN DE PRIORIDADES:**

**R1 – Prioridad Media**

La lentitud del sistema afecta la productividad de los empleados, pero permite continuar trabajando aunque sea de forma limitada. No detiene completamente las operaciones, por lo que su atención puede ser posterior a problemas más críticos.

**R2 – Prioridad Alta**

La pérdida o sobreescritura de documentos impacta directamente la información administrativa y de clientes. Este problema puede generar errores legales, pérdida de datos importantes y desconfianza interna, lo que lo convierte en un requerimiento crítico.

**R3 – Prioridad Alta**

Las fallas inesperadas del sistema detienen completamente las operaciones de la empresa durante la jornada laboral. Esto genera interrupciones totales del trabajo, pérdida de tiempo y posibles pérdidas económicas, por lo que su atención es prioritaria.

**6. ANÁLISIS BÁSICO DE INFRAESTRUCTURA:**

**6.1 - Requerimientos analizados (alta prioridad):**

**R2**: El sistema debe garantizar que los documentos no se pierdan ni se sobrescriban accidentalmente.

**R3**: El sistema debe estar disponible y no fallar de forma inesperada durante la jornada laboral.

**6.2 - Recursos de infraestructura involucrados:**

**R2:** 

**Procesamiento:**
Gestiona las operaciones de acceso, guardado y control de archivos por múltiples usuarios.

**Memoria:**
Permite manejar archivos abiertos simultáneamente y procesos de escritura sin errores.

**Almacenamiento:**
Es el componente principal donde se guardan los documentos administrativos y de clientes.

**Red:**
Facilita el acceso concurrente a los documentos desde distintas áreas de la empresa.


**R3:**

**Procesamiento:**
Ejecuta los servicios principales del sistema durante la jornada laboral.

**Memoria:**
Mantiene activos los procesos necesarios para el funcionamiento continuo del sistema.

**Almacenamiento:**
Permite acceder a la información necesaria para operar el sistema.

**Red:**
Conecta a los usuarios con el sistema interno de la empresa.

**6.3 - Riesgos técnicos y puntos unicos d ** 

| Requerimiento | Riesgo identificado | Posible SPOF | Justificación |
|--------------|--------------------|--------------|---------------|
| Req. 2 | Conflictos al guardar archivos simultáneamente pueden provocar pérdida o sobrescritura de documentos. | Almacenamiento central de documentos | La modificación concurrente sin control puede generar inconsistencias y pérdida de información. Si el almacenamiento falla, los documentos quedan inaccesibles. |
| Req. 3 | Sobrecarga de recursos durante horas pico puede provocar caídas inesperadas del sistema. | Equipo o sistema central | El uso simultáneo puede superar la capacidad disponible. Si el sistema central falla, toda la operación se detiene. |








<!--stackedit_data:
eyJoaXN0b3J5IjpbNTk3MzQ0ODYsMjA3MTUwODQ0MiwxMDEyMz
MzNTQzLC05MDkxNzU0NTksLTc0OTU1NjQwNiwtNTgxMjI3MDks
MTg1Mjg2MzQyMSw1NjU3NDI4MDVdfQ==
-->