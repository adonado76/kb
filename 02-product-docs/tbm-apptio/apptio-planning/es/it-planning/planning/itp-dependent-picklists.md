---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Filtros de partida individual (listas de selección dependientes)"
breadcrumb:
  - "Planning"
  - "Configuración y administración"
source_path: "it-planning/planning/itp-dependent-picklists.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Filtros de partida individual (listas de selección dependientes)

Nota: *Se requieren roles de administrador o responsable del proceso presupuestario para gestionar los filtros de partidas.*

**Los filtros de elementos de línea** le permiten controlar qué valores aparecen en un campo desplegable en función de las selecciones realizadas en otra columna. Esto mejora la precisión de la introducción de datos al evitar que los usuarios vean opciones irrelevantes o no válidas.

Por ejemplo:

- Cuando un usuario selecciona un **centro de costes**, puede restringir el menú desplegable **Cuenta** para que solo muestre las cuentas asociadas a ese centro de costes.
- Los filtros se pueden encadenar para crear dependencias multinivel (por ejemplo, Centro de costes → Cuenta → Proveedor).

**Importante:**

Los filtros de elementos de línea solo afectan a lo que se muestra en el menú desplegable. No modifican los datos ya introducidos.

**Ejemplo**

Dado el siguiente mapeo:

|  |  |
| --- | --- |
| **Cuenta** | **Centro de costes** |
| ACCT\_6000 | **CC-200** |
| ACCT\_6100 | **CC-200** |
| ACCT\_6200 | **CC-200** |
| ACCT\_3001 | **CC-200** |
| ACCT\_3002 | CC-210 |
| ACCT\_3011 | CC-210 |
| ACCT\_2006 | CC-220 |
| ACCT\_4021 | CC-220 |

Si un usuario selecciona **Centro de costes = CC-200**, el menú desplegable **Cuenta** solo mostrará:

- ACCT\_6000
- ACCT\_6100
- ACCT\_6200
- ACCT\_3001

## Crear un filtro de partidas

1. Vaya a **Configuración** → **Filtros de partidas individuales**.
2. Selecciona **Añadir** (➕) en la esquina superior derecha. Se abre el cuadro de diálogo **Añadir filtro de línea.**
3. Introduzca los siguientes datos:
   1. **Nombre** : un nombre de filtro único
   2. **Columna** : la dimensión que desea filtrar
   3. **Filtrar por** : el atributo cuyo valor determina las opciones filtradas
4. Seleccione **Añadir** para crear el filtro.
5. Seleccione el filtro de la tabla.
6. Exportar la plantilla de filtro:
   1. Seleccione el **menú con los tres puntos** → **Exportar a archivo**, o haga clic con el botón derecho del ratón en el filtro y seleccione **Exportar a archivo**.
   2. También puede exportar una plantilla en blanco a través **del menú Ellipsis** → **Exportar plantilla.**
7. Rellene el archivo CSV:
   1. Añadir filas que asignen valores **de columna** a valores **de filtro por**
   2. Para las dimensiones que utilizan **el código** como identificador único, debe utilizar el código (no el nombre).
   3. Cada fila solo puede tener un valor por columna.
8. Importar la asignación:
   1. Seleccione **el menú Ellipsis** → **Importar desde archivo**, o haga clic con el botón derecho del ratón en el filtro y seleccione **Importar desde archivo.**
   2. Sube el archivo CSV.

## Actualizar un filtro de partidas

1. Vaya a **Configuración** → **Filtros de líneas de pedido** y seleccione el filtro que desea actualizar.
2. Exporta la asignación actual utilizando **el menú Elipsis** → **Exportar a archivo**.
3. Edita el CSV para añadir, modificar o eliminar filas.
4. Importe el CSV actualizado utilizando **el menú Ellipsis** → **Importar desde archivo**.

   Las asignaciones actualizadas entran en vigor inmediatamente.

## Borrar un filtro de partidas

1. Vaya a **Configuración** → **Filtros de partidas individuales**.
2. Haga clic con el botón derecho del ratón en el filtro que desea eliminar y seleccione **Eliminar**.

Una vez eliminado, el filtro ya no se aplica a los menús desplegables de ninguna tabla de partidas individuales.
