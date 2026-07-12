---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Guía práctica 2: Controlar el acceso mediante la asignación de usuarios"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Trabajar con datos"
  - "Seguridad de datos"
source_path: "studio/new-uc/howtoguides/work-with-data/htg-cacc.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Guía práctica 2: Controlar el acceso mediante la asignación de usuarios

## Objetivo

Crea y gestiona tablas de correspondencias que definan qué usuarios pueden acceder a qué datos, lo que permite aplicar controles de seguridad granulares a nivel de fila.

## Cuándo se utiliza

Antes de implementar RLS en cualquier tabla de datos. Utilícelo también al añadir nuevos usuarios al sistema, cuando cambien los límites organizativos o al implementar diferentes niveles de acceso (por ejemplo, acceso regional frente a acceso global).

## Tiempo estimado

Entre 20 y 30 minutos para la configuración inicial; entre 5 y 10 minutos para las actualizaciones

## Requisitos previos

- Acceso al proyecto «Row-Level Security»
- Lista de usuarios y sus permisos de acceso
- Conocer las dimensiones de datos que desea filtrar (por ejemplo, unidades de negocio, centros de coste)

## Paso 1: Planifica la estructura de tu tabla de correspondencias

Antes de crear tablas, planifica tu estrategia de control de acceso:

- **Identifica el criterio de filtrado:** ¿En qué columna(s) de tus datos vas a aplicar el filtro? Ejemplos habituales: unidad de negocio, centro de costes, región, departamento.
- **Determina los patrones de acceso:** ¿Tendrán algunos usuarios acceso restringido, mientras que otros tendrán acceso completo? ¿Hay algún usuario que necesite acceder a varios valores?
- **Decida cómo organizar las tablas:** es posible que necesite varias tablas de correspondencia para distintos escenarios de acceso (por ejemplo, una para usuarios estándar y otra para usuarios con «acceso completo»).

Una tabla de correspondencias solo necesita dos columnas:

|  |  |  |
| --- | --- | --- |
| **Columna** | **Descripción** | **Ejemplo** |
| ID de usuario | El correo electrónico de inicio de sesión del usuario. Debe coincidir exactamente con el nombre de usuario de la tabla «Usuarios». | bob@acme.com |
| Elemento | El valor al que puede acceder el usuario, tal y como aparece en tus tablas de datos. | BU 2 |

Consejo: En esta fase, no tienes que preocuparte por el nombre de la tabla ni por los nombres de las columnas. Al configurar los filtros de RLS, deberá seleccionar la tabla y las columnas adecuadas en los menús desplegables.

## Paso 2: Crea tu archivo de tabla de correspondencias

Prepara tu tabla de correspondencias como un archivo de « CSV » o Excel fuera de TBM Studio:

1. Abre tu aplicación de hoja de cálculo (Excel, Google Sheets, etc.).
2. Crea columnas para el ID de usuario y los elementos a los que los usuarios pueden acceder.
3. Introduce una fila por cada asignación de usuario a elemento. Si un usuario tiene acceso a varios elementos, incluye varias filas para ese usuario.
4. Guarda el archivo en form CSV o o Excel.

**Ejemplo: Tabla de acceso estándar a las unidades de negocio**

|  |  |
| --- | --- |
| **ID de usuario** | **Unidad de negocio** |
| bob@acme.com | BU 2 |
| rachel@acme.com | BU 1 |
| rachel@acme.com | BU 3 |
| tom@acme.com | BU 1 |
| tom@acme.com | BU 2 |
| tom@acme.com | BU 3 |

*En este ejemplo, Bob solo ve los datos de la unidad de negocio 2, Rachel ve los de la unidad de negocio 1 y la 3, y Tom ve los de las tres unidades de negocio.*

**Ejemplo: Tabla de acceso completo (para usuarios que deben poder ver todo)**

|  |  |
| --- | --- |
| **ID de usuario** | **Es administrador** |
| sally@acme.com | Sí |
| director@acme.com | Sí |

*Esta tabla independiente se utiliza con la lógica OR en los filtros RLS para conceder acceso completo sin necesidad de enumerar todos los valores posibles de BU.*

## Paso 3: Cargar la tabla de correspondencias en el proyecto RLS

1. Abre el menú **«Configuración»** y haz clic en «**Configurar seguridad a nivel de fila** ».
2. En el proyecto «Row-Level Security», haz clic en **Nuevo** > **Tabla**.
3. Introduzca un nombre descriptivo para la tabla (por ejemplo, «Acceso a BU» o «Permisos de centros de coste»).
4. Selecciona **«Subir archivo»** y elige el archivo de « CSV » o Excel que hayas preparado.
5. Comprueba la detección de columnas. Asegúrese de que las columnas «ID de usuario» y «Elemento» estén correctamente identificadas.
6. Haz clic en **«Crear»** para subir la tabla.

## Paso 4: Comprueba la subida

1. Abre la tabla cargada desde el Explorador de proyectos.
2. Revisa los datos para asegurarte de que todos los ID de usuario y los elementos se muestran correctamente.
3. Comprueba que los tipos de datos de las columnas sean los adecuados (normalmente «Etiqueta» o «Texto» para ambas columnas).
4. Marca la casilla de la tabla para que esté disponible para la configuración de RLS.

## Alternativa: cargar tablas de asignación a través de DataLink

En el caso de organizaciones con muchos usuarios o cambios frecuentes en los permisos, puede automatizar las actualizaciones de las tablas de asignación mediante DataLink (clásico):

1. Accede a tu instancia de « DataLink » (clásica).
2. Seleccione el agente y el conector que desee.
3. En la sección **«Proyecto»**, escribe «Usuarios» para seleccionar el proyecto «Seguridad a nivel de fila».
4. Realiza la configuración como lo harías para cualquier ejecución de « DataLink ».

## Paso 5: Actualizar las tablas de correspondencias cuando se produzcan cambios en el acceso

Los permisos de acceso de los usuarios cambian con el tiempo. A continuación te explicamos cómo mantener tus tablas de correspondencias:

**Añadir un nuevo usuario:**

- Añade una o varias filas nuevas a la tabla de correspondencias con el correo electrónico del usuario y los elementos que tiene autorizados.
- Si utiliza la opción de carga de archivos, vuelva a cargar el archivo completo actualizado.

**Modificar el acceso de un usuario:** modifica las filas correspondientes a ese usuario (añade nuevas filas de elementos y elimina las antiguas) y vuelve a subir el archivo.

**Eliminar el acceso de un usuario:** Elimina todas las filas correspondientes a ese usuario de la tabla de asignación.

## Resultados previstos

- Las tablas de asignación aparecen en el Explorador de proyectos del proyecto de seguridad a nivel de fila.
- Las tablas contienen correspondencias precisas entre usuarios y elementos.
- Las tablas están disponibles para su selección al configurar los pasos de RLS en las tablas de datos.

## Errores habituales y solución de problemas

**Discrepancia en el ID de usuario:** los ID de usuario deben coincidir exactamente con los nombres de usuario de la tabla «Usuarios». Comprueba si hay errores ortográficos, espacios de más o diferencias en mayúsculas y minúsculas.

**Discrepancia en los valores de los elementos:** los valores de los elementos deben coincidir exactamente con los valores de tus tablas de datos. Si tus datos incluyen «Unidad de negocio 1», pero la tabla de correspondencias indica «UB 1», RLS no funcionará correctamente.

**Falta de usuarios con acceso completo:** si añade nuevos elementos (por ejemplo, una nueva unidad de negocio), los usuarios a los que se les ha concedido acceso a través de la tabla de asignación estándar no verán automáticamente los nuevos datos a menos que actualice sus entradas. Considera la posibilidad de utilizar una tabla independiente con «acceso completo» para los usuarios que deban tener siempre acceso a todos los datos.

**Tema principal:** [Seguridad de los datos](../../../../studio/new-uc/howtoguides/work-with-data/data-security.html)
