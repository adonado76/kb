---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Implementar la seguridad a nivel de fila para el acceso de los usuarios"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Gestionar usuarios y permisos"
  - "Control de accesos"
source_path: "studio/new-uc/howtoguides/manage-users-permission/implement-rls.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Implementar la seguridad a nivel de fila para el acceso de los usuarios

|  |  |
| --- | --- |
| **Objetivo** | Configure las asignaciones entre usuarios y datos para que los usuarios solo vean las filas para las que tienen autorización |
| **Tiempo estimado** | Entre 30 y 45 minutos para la configuración inicial; mantenimiento continuo a medida que cambian los usuarios |
| **Requisitos previos** | Rol de administrador o usuario avanzado; usuarios configurados en el proyecto; conocimiento de los requisitos de segmentación de datos |

## Cuándo utilizar este procedimiento

Utilice la seguridad a nivel de fila cuando los usuarios deban ver diferentes subconjuntos de datos en función de su identidad. Entre los casos más habituales se encuentran los directores de unidades de negocio que solo ven los costes de su departamento, los directores regionales que solo acceden a los datos de su región o los responsables de centros de coste distribuidos que revisan sus propios presupuestos.

Esta guía se centra en el aspecto de la asignación de usuarios de RLS. Para obtener información sobre la implementación técnica completa, incluida la configuración del proceso de transformación, consulte **la sección « 3.1.4: : Seguridad de los datos** ».

## Comprender la arquitectura de RLS

La seguridad a nivel de fila en TBM Studio consta de dos componentes principales:

- **Tablas de asignación:** define qué usuarios pueden acceder a qué elementos de datos (por ejemplo, el usuario bob@acme.com puede ver la Unidad de Negocio 2)
- **Filtros RLS:** se aplican a las tablas de transformación para garantizar el cumplimiento de las reglas de asignación cuando los usuarios visualizan los informes

Las tablas de asignación se almacenan en el proyecto **«Row-Level Security»**, que se instala automáticamente al crear una nueva instancia de TBM Studio y se aplica a todos los proyectos de un dominio.

## Pasos

## Paso 1: Planifica la estructura de tu RLS

Antes de crear tablas de correspondencia, determine:

- ¿Por qué criterio vas a filtrar? (por ejemplo, unidad de negocio, centro de costes, región)
- ¿Qué usuarios necesitan acceder a qué valores de esa dimensión?
- ¿Hay usuarios que necesiten acceso a todos los datos? (Es posible que necesites una tabla de correspondencias independiente con «acceso completo»)

## Paso 2: Crear la tabla de correspondencias

1. Abre el menú «Configuración» y haz clic en «**Configurar seguridad a nivel de fila** ».
2. Crea una nueva tabla (o prepárala externamente en formato Excel/ CSV ) con dos columnas obligatorias:
   - **ID:** El ID de usuario (dirección de correo electrónico que coincide con la tabla «Usuarios»)
   - **Elemento:** El valor al que puede acceder el usuario (por ejemplo, «BU 2», «América del Norte»)
3. Rellena la tabla de correspondencias con las asociaciones entre usuarios y elementos. Por ejemplo:

   |  |  |
   | --- | --- |
   | **Nº Propuesta** | **Unidad de negocio** |
   | bob@acme.com | BU 2 |
   | rachel@acme.com | BU 1 |
   | rachel@acme.com | BU 3 |

   Consejo: Si un usuario necesita acceder a varios valores, incluye varias filas para ese usuario (tal y como se muestra para « rachel@acme.com » más arriba).
4. Sube la tabla de correspondencias al proyecto de seguridad a nivel de fila.

## Paso 3: Crear una asignación con acceso completo (opcional)

Para los usuarios que necesitan ver todos los datos (por ejemplo, directivos o administradores financieros), cree una tabla independiente con acceso completo en lugar de enumerar todos los valores posibles:

|  |  |
| --- | --- |
| **Nº Propuesta** | **Es administrador** |
| sally@acme.com | Sí |

Este enfoque garantiza que los usuarios con acceso completo vean automáticamente los nuevos elementos de datos sin necesidad de actualizar su asignación.

## Paso 4: Aplicar filtros RLS a las tablas

Una vez que las tablas de correspondencia estén listas, aplícalas a tus tablas de datos. Para obtener instrucciones detalladas sobre cómo configurar los pasos del proceso de RLS, consulte **la sección « 3.1.4:** : Seguridad de los datos».

## Paso 5: Comprobar la configuración de RLS

- Utiliza el **filtro de vista previa** en el paso RLS para comprobar qué verán usuarios concretos
- Utiliza la función **«Suplantar identidad»** para ver los informes como un usuario concreto
- Comprueba que los usuarios con acceso completo puedan ver todos los datos
- Asegúrate de que los usuarios con restricciones solo vean los datos a los que tienen acceso

## Comportamiento del RLS en las distintas funciones

Comprender cómo funciona RLS en las distintas funciones de TBM Studio:

- **Tablas de transformación:** RLS filtra las filas antes de que los datos aparezcan en cualquier uso posterior
- **Tablas editables:** RLS limita las filas que los usuarios pueden ver Y editar. Los usuarios solo pueden modificar las filas visibles.
- **Informes:** las agregaciones reflejan únicamente los datos filtrados que el usuario puede ver
- **Publicación:** cuando los usuarios publican tablas editables, las filas ocultas se conservan, no se eliminan
- **Informes generales de modelos:** cada nivel refleja únicamente el RLS aplicado a ese nivel concreto; es posible que la suma de los valores no coincida con los totales que se muestran en los niveles superiores

Importante: Las tablas no heredan automáticamente la configuración de RLS. Debes añadir un paso RLS para cada tabla que requiera filtrado a nivel de fila.

## Errores habituales

- **ID de usuario no coincidentes:** La columna «ID» de la tabla de asignación debe coincidir exactamente con el ID de usuario de la tabla «Usuarios». Incluso las diferencias más insignificantes (distinción entre mayúsculas y minúsculas, espacios de más) hacen que RLS falle.
- **Elusión de privilegios de administrador:** No confíe en RLS para proteger los datos frente a los usuarios con privilegios de administrador. Pueden acceder al modo Studio y modificar la configuración de RLS.
- **Costes asignados:** si se asignan costes de áreas restringidas a áreas visibles, los usuarios pueden ver costes que se originaron fuera de su ámbito de autorización.
- **Falta de RLS en las tablas de desglose:** Asegúrese de que RLS esté configurado en todas las tablas que aparecen en los informes de desglose.

## Tareas relacionadas

- [Configurar los pasos del proceso de RLS](../work-with-data/htg-arls.html)
- Cargar datos RLS a través de DataLink (Sección 5.1 )
- [Comprender el modelo de seguridad](../../concepts-architecture/studio-model/security-architecture.html) (Sección 4.4 )

**Tema principal:** [Control de acceso](../../../../studio/new-uc/howtoguides/manage-users-permission/access-control-intro.html)
