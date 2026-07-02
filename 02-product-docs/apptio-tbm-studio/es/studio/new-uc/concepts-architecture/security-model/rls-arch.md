---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "RLS Arquitectura"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Modelo de seguridad"
  - "Seguridad a nivel de fila (RLS)"
source_path: "studio/new-uc/concepts-architecture/security-model/rls-arch.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# RLS Arquitectura

La implementación de RLS requiere dos componentes clave: tablas de correspondencias que definen las relaciones entre usuarios y datos, y reglas de filtrado que aplican esas relaciones a las tablas de datos.

**El proyecto de seguridad a nivel de fila**

RLS se gestiona a través de un proyecto específico denominado «Row-Level Security». Este proyecto se instala automáticamente al crear una nueva instancia de Apptio y se aplica a todos los proyectos de un dominio. Para acceder a ella, ve al menú «Configuración» y haz clic en «Configurar seguridad a nivel de fila».

**Tablas de correspondencias**

Las tablas de asignación definen qué datos puede ver cada usuario. Una tabla de correspondencias debe tener al menos dos columnas:

- **ID de usuario:** la dirección de correo electrónico del usuario, que debe coincidir con su ID de usuario en la tabla «Usuarios».
- **Elemento:** El valor que el usuario está autorizado a ver, tal y como aparece en la tabla de datos protegida (por ejemplo, el nombre de una unidad de negocio, el código de un centro de coste o el nombre de un centro de datos).

**Ejemplo — Tabla de asignación de accesos de la unidad de negocio:**

|  |  |
| --- | --- |
| **ID de usuario** | **Unidad de negocio** |
| bob@acme.com | BU 2 |
| rachel@acme.com | BU 1 |
| rachel@acme.com | BU 3 |
| tom@acme.com | BU 1 |

En este ejemplo, Bob solo puede ver los datos de la unidad de negocio 2. Rachel puede ver la BU 1 y la BU 3. Tom solo puede ver la unidad 1. Fíjate en que Rachel tiene dos filas: una para cada unidad de negocio a la que tiene permiso de acceso.

**Patrón de acceso completo**

Para los usuarios que necesitan ver todos los datos (como los directivos o analistas responsables de toda la organización), se puede crear una tabla de correspondencias independiente con una columna de indicador, en lugar de enumerar todos los valores posibles.

|  |  |
| --- | --- |
| **ID de usuario** | **Es administrador** |
| sally@acme.com | Sí |
| cfo@acme.com | Sí |

A continuación, se añade una columna de fórmula a la tabla protegida cuyo resultado sea siempre «Sí», y se crea una regla de filtro RLS utilizando la lógica «O»: el usuario debe aparecer en la tabla de asignación estándar correspondiente a sus unidades de negocio específicas, O bien debe aparecer en la tabla de acceso completo. Este enfoque se adapta automáticamente cuando se añaden nuevas unidades de negocio; no es necesario actualizar los datos de los usuarios con acceso completo.

**Lógica de filtrado**

Las reglas de filtrado RLS vinculan las tablas de asignación con las tablas de datos. Cada regla de filtrado consta de cuatro componentes:

1. **Columna de la tabla:** la columna de la tabla de datos que contiene los elementos que se van a filtrar (como la columna «BU» en «Cost Source»).
2. **Tabla de asignación:** la tabla de asignación que contiene las definiciones de RLS (como el acceso a la unidad de negocio).
3. **Columna de asignación:** la columna de la tabla de asignación que contiene los valores permitidos (como la columna «Unidad de negocio» en BU Access).
4. **Columna de usuario:** la columna de la tabla de correspondencias que contiene los ID de usuario (como la columna «ID de usuario» en BU Access).

Cuando se definen varias entradas de filtro, se aplica por defecto la lógica «O»: si alguna de las entradas es verdadera, el usuario puede ver la fila. Así es como funciona el patrón de acceso completo: el usuario aparece en la tabla de asignación estándar O bien aparece en la tabla de acceso completo.

**Tema principal:** [Seguridad a nivel de fila (RLS)](../../../../studio/new-uc/concepts-architecture/security-model/row-level-security.html)
