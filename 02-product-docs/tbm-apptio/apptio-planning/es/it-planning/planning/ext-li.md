---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Partidas exteriores"
breadcrumb:
  - "Planning"
  - "Trabajar con planos"
source_path: "it-planning/planning/ext-li.html"
images:
  - "resources/images/it_planning_images/edit-mli.png"
  - "resources/images/it_planning_images/edit-mode.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Partidas exteriores

Las partidas externas le permiten gestionar los datos del plan que se originan en sistemas externos e introducirlos en Apptio Planning para su visibilidad y análisis, sin permitir que los usuarios finales los editen.

Nota: Se requieren roles de administrador o responsable del proceso presupuestario para gestionar partidas externas.

**Dispositivos clave**

- Las partidas externas se pueden importar a las pestañas **Finanzas** (Resumen y Otros), **Contratos**, **Activos, Mano de obra** y **Actividad laboral**.
- Se marcan con **Is External = true** en el momento de la importación.
- **Los Propietarios de Centros de Coste no pueden editar** partidas externas - son de sólo lectura.
- Solo **los administradores o los propietarios del proceso presupuestario** pueden importar partidas externas.
- Solo los usuarios con **ExternalLineEdit** permiso pueden editar elementos de línea externos.

## Importar partidas externas

Puede importar datos externos desde la **vista heredada** o desde la **nueva vista**.

1. Vaya a Gastos y seleccione la pestaña a la que desea importar las líneas externas ( **Resumen**, **Contratos**, **Activos, Mano de obra, Actividad laboral u Otros).**
2. **Elija la Vista adecuada:**
   1. **Vista heredada** → Haga clic en el menú **Acciones**
      1. Seleccione **Importar finanzas externas..**., **Importar contratos externos...**, o **Importar activos externos...**
   2. **Nueva vista** → Haga clic en **el menú de elipsis (...)** en la tabla
      1. Seleccione **Importar finanzas externas..**., **Importar contratos externos...**, o **Importar activos externos...**
3. Seleccione **Reemplazar todo** (sobrescribir todos los datos externos existentes) o **Actualizar datos** (actualizar los códigos de partida que coincidan).
4. Complete la carga para consignar las partidas externas.

## Editar elementos de línea externos

Las partidas externas solo se pueden editar en la **vista Nueva** vista.

Los usuarios deben tener el **ExternalLineEdit** permiso (concedido por defecto a los roles de administrador y propietario del proceso presupuestario).

**Editar una sola línea externa**

1. Haga clic con el botón derecho del ratón en la línea externa.
2. Seleccione **Editar línea externa** para activar el modo de edición.
3. Haga clic en **Salir del modo de edición** para volver a todos los elementos de línea.

**Editar varias líneas externas**

1. Seleccione una o más líneas externas utilizando las casillas de verificación.
2. Abre el **menú de puntos suspensivos (...)** en la tabla.
3. Seleccione **Editar <tipo de elemento de línea> externo seleccionado...**, dependiendo de la pestaña que esté editando.
4. Haga clic en **Salir del modo de edición** para volver a todos los elementos de línea.

![](../../../../../03-media/apptio-planning/resources/images/it_planning_images/edit-mli.png)

**Habilitar el modo de edición para todas las líneas externas**

1. Abre los **puntos suspensivos (...) menú** sobre la mesa.
2. Seleccionar **Editar todos los <tipo de elemento de línea> externos...**
3. Todas las líneas externas entran en modo de edición.
4. Seleccione **Salir del modo de edición** para guardar todos los cambios y volver a todas las partidas.

![](../../../../../03-media/apptio-planning/resources/images/it_planning_images/edit-mode.png)

**Eliminación de líneas externas**

1. En el modo Edición, seleccione una o varias líneas externas mediante las casillas de verificación.
2. O bien:
   1. Haga clic con el botón derecho y seleccione **Eliminar**, o
   2. Utilice el botón **Eliminar** de la barra de herramientas de la tabla.
