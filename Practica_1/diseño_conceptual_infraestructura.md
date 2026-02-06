**Nombre**: Walter Vladimir Cantor Claros --> WC100218

**INTRODUCCIÓN:**
En este documento se presenta el diseño conceptual de una infraestructura de servidores, elaborado a partir de requerimientos previamente analizados y priorizados. El objetivo es proponer una arquitectura lógica de alto nivel que permita visualizar los componentes necesarios y su relación, sin considerar marcas, modelos ni configuraciones específicas.

**REQUERIMIENTOS CONSIDERADOS:**

**R1** - Protección de la información contra accesos no autorizados.

**Descripción:** mantener el control y seguridad de la información es esencial para cualquier empresa por ese motivo elegimos este requerimiento para protección de los datos y mantener también un control con entre los empleados.

**R2** - Acceso simultáneo de multiples usuarios sin afectar el funcionamiento del sistema.

**Descripción:** permite a los usuarios trabajar de una manera más eficiente y que ellos se conecten simultáneamente sin problema alguno y mantener la eficiencia en un buen rendimiento.

**IDENTIFICACIÓN DE SERVIDORES POR ROL:**

A partir de los requerimientos, se identifican los siguientes roles de servidores:

| Requerimiento | Rol del servidor | Justificación |
|---------------|-----------------|---------------|
| R1 – Protección de la información contra accesos no autorizados | Servidor de Base de Datos | Centraliza la información sensible y permite mantenerla protegida de accesos directos no autorizados. |
| R1 – Protección de la información contra accesos no autorizados | Servidor de Aplicación | Funciona como intermediario entre los usuarios y los datos, evitando accesos directos a la información crítica. |
| R2 – Acceso simultáneo de múltiples usuarios sin afectar el funcionamiento del sistema | Servidor de Presentación | Permite que varios usuarios accedan al sistema de forma concurrente sin afectar el rendimiento general. |
| R2 – Acceso simultáneo de múltiples usuarios sin afectar el funcionamiento del sistema | Servidor de Aplicación | Gestiona múltiples solicitudes al mismo tiempo, asegurando el correcto funcionamiento del sistema. |

**DISEÑO CONCEPTUAL DE LA ARQUITECTURA:**



<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1MjkxMTMyNzcsLTkzMDcxMjUzNCwtMT
I1NTM4NDEyNV19
-->