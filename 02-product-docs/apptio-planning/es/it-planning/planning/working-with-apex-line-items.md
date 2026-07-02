---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Trabajar con partidas Apex"
breadcrumb: []
source_path: "it-planning/planning/working-with-apex-line-items.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Trabajar con partidas Apex

En este tema se explica cómo gestionar las partidas de Apex en la aplicación, lo que incluye añadir, insertar, duplicar, importar, exportar y eliminar partidas.

## Antes de empezar

Todas las funciones enumeradas aquí sólo están disponibles para los clientes que no disponen de PFP o SDP. Cuando un administrador o propietario del proceso presupuestario activa la función Tabla de partidas de Apex, los usuarios sin rol de administrador pueden cambiar la vista de la tabla entre `Classic View` y `New View`.

## Procedimiento

- Añadir partidas:
  1. Encima de la tabla de partidas, seleccione el icono (Imagen del signo más (+)).
  2. En la ventana `New Line Item` , seleccione los atributos de la nueva línea.
  3. Seleccione `Add` para añadir la partida.

     Alternativamente, seleccione `Add Another` para añadir más partidas, y seleccione `Add` para añadir las partidas.
  4. Para añadir atributos opcionales, haga doble clic en la celda de la tabla e introduzca los detalles.
- Insertar partidas:
  1. Haz clic con el botón derecho en una fila.
  2. Seleccione Insertar fila arriba o Insertar fila abajo para insertar una fila.
  3. En la ventana Nueva partida, seleccione los atributos de la nueva partida.
  4. Seleccione Añadir para añadir la partida.

     Seleccione Añadir otra para añadir más partidas y seleccione Añadir para añadir las partidas.
  5. Para añadir atributos opcionales, haga doble clic en la celda de la tabla e introduzca los detalles.
- Borrar partidas:
  1. Haga clic con el botón derecho del ratón en la partida.
  2. Seleccione la opción Borrar. Aparecerá una ventana emergente de confirmación.
  3. Introduzca la dirección `LineItem Code` y seleccione Borrar.
- Partidas duplicadas:
  1. Haga clic con el botón derecho del ratón en la partida.
  2. Seleccione Duplicar Fila.
- Importar partidas:
  1. Encima de la tabla de Gastos, seleccione el icono Opciones.
  2. Para importar partidas individuales externas, seleccione Importar finanzas externas.

     Alternativamente, para importar partidas no externas, seleccione Importar finanzas.
- Exportar partidas:
  1. Encima de la tabla de Gastos, seleccione el icono Opciones.
  2. Para exportar una plantilla de tipo de gasto, seleccione Exportar plantilla de finanzas.

     Alternativamente, para exportar partidas, seleccione Exportar finanzas.
- Información sobre lista de selección dependiente

  Cuando selecciona una opción en una columna, puede restringir las opciones que pueden seleccionarse en otra columna, ya que Planning excluye automáticamente las opciones que serían incompatibles con la opción que ha seleccionado en la primera columna.

  Por ejemplo, cada proyecto puede utilizar un conjunto diferente de centros de coste. Cuando se cambia el Centro de costes de una línea, también cambia la lista de opciones que pueden seleccionarse para el Proyecto en esa línea. Estas opciones pueden ser un subconjunto de todos los proyectos disponibles en el entorno.

  Los usuarios pueden encontrar esto confuso porque ven una lista diferente de opciones para diferentes filas en la misma columna.

  Ahora se muestra un icono de información sobre herramientas en la celda de la tabla (Añadir imagen de la información sobre herramientas de la lista de selección Dependiente dep\_tool\_pick.png )

  Al pasar el ratón por encima de la información sobre herramientas, se muestra un mensaje específico de la columna, que explica qué columna es la responsable de filtrar las opciones de la lista. (Añadir imagen de la información sobre herramientas de la lista desplegable Dependiente dep\_tool\_pick1.png )

  Esta función sólo está disponible en las tablas de partidas de Apex. No está disponible en las tablas clásicas de partidas.

  Los filtros de partidas aún no son compatibles con las tablas de partidas de Apex. Cuando las tablas de artículos de línea de Apex admiten filtros de artículos de línea, las columnas filtradas por la configuración del filtro de artículos de línea utilizarán la información sobre herramientas de la lista de selección dependiente.
- Borrar gastos en bloque:
  1. En el menú de navegación, seleccione Gastos > Nueva vista.
  2. Seleccione las líneas que desea eliminar haciendo clic en la casilla de verificación o utilizando `SHIFT + down
     arrow` desde el teclado para seleccionar varias líneas
  3. Seleccione el icono (Eliminar imagen de icono) en la barra de menú situada encima de la tabla. También puede realizar la misma operación desde el menú contextual haciendo clic con el botón derecho del ratón.
  4. Aparece un cuadro de diálogo de confirmación de eliminación.
  5. Nota: Cuando la vista de gastos está agrupada por una o más columnas, las operaciones a nivel de fila como añadir fila, copiar fila, eliminar fila y duplicar fila no están disponibles.

     Introduzca los datos de confirmación en la casilla de confirmación y seleccione el botón `Delete` .
