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

### Arquitectura lógica por capas

####  Capa de Presentación

-   Usuarios de oficina central
    
-   Usuarios de sucursales
    
-   Servidor de presentación
    

**Función:**  
Recibir las solicitudes de múltiples usuarios y mostrar la información del sistema.

----------

####  Capa de Aplicación

-   Servidor de aplicación
    

**Función:**  
Procesar las reglas del negocio, controlar accesos y administrar las solicitudes simultáneas de los usuarios.

----------

#### Capa de Datos

-   Servidor de base de datos
    

**Función:**  
Almacenar y proteger la información financiera y de clientes.

----------

### Componentes expuestos y protegidos

-   **Componentes expuestos:**
    
    -   Servidor de presentación (punto de acceso para los usuarios)
        
-   **Componentes protegidos en la red interna:**
    
    -   Servidor de aplicación
        
    -   Servidor de base de datos

**DIAGRAMA LÓGICO DE INFRAESTRUCTURA:**

```mermaid
flowchart TD
    U[Usuarios]
    SP[Servidor de Presentación]
    SA[Servidor de Aplicación]
    BD[Servidor de Base de Datos]

    U --> SP
    SP --> SA
    SA --> BD
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTAyMDU5MDEwNCwtMTU2MDYyNzI1NywxNT
YwMTk4NDU3LC0xNTI5MTEzMjc3LC05MzA3MTI1MzQsLTEyNTUz
ODQxMjVdfQ==
-->