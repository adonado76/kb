---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Instantáneas (control de versiones)"
breadcrumb:
  - "Planning"
  - "Flujos de trabajo y colaboración"
source_path: "it-planning/planning/snapshots.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Instantáneas (control de versiones)

Una instantánea es una copia de una versión del plan con marca de tiempo y de solo lectura. Las instantáneas conservan vistas históricas de un plan para que puedas comparar los planes enviados, aprobados o finalizados con versiones anteriores.

Las instantáneas son especialmente útiles para:

- Seguimiento de los cambios entre envíos
- Comparación de los valores presupuestarios actuales con versiones anteriores
- Auditoría de actualizaciones durante el ciclo de planificación

Las instantáneas **no** se pueden editar y solo están disponibles para **los departamentos secundarios**.

## Cuando las instantáneas se crean automáticamente

Apptio La planificación crea automáticamente instantáneas durante los puntos clave del proceso de planificación:

- Cuando se **presenta** un plan
- Cuando el estado de un plan cambia de **Nuevo → Abierto**

Estas instantáneas automáticas garantizan que siempre haya disponible una versión de referencia para realizar comparaciones.

## Crear una instantánea manualmente

Puede crear instantáneas adicionales en cualquier momento para sus propias necesidades de comparación o análisis.

**Pasos para crear una instantánea**

1. En el menú **Plan**, selecciona el plan en el que deseas trabajar.
2. Navega a **Plan → Gastos**.
3. En el menú desplegable **Departamento**, seleccione un **departamento secundario**.
4. Abre el menú desplegable **Versiones del plan**.
5. Seleccione **Guardar instantánea**.
6. Introduzca un **nombre** para la instantánea.
7. Haga clic en **Crear**.

Tu instantánea ya está guardada y puedes acceder a ella en cualquier momento.

## Acceso a instantáneas guardadas

Para ver las instantáneas existentes:

1. Siga la misma ruta de navegación: **Plan → Gastos**.
2. En el menú desplegable **Versiones del plan**, verás todas las instantáneas guardadas disponibles para el departamento seleccionado.

Las instantáneas son siempre de solo lectura para preservar la precisión histórica.

## Uso de instantáneas para realizar comparaciones

Las instantáneas se pueden seleccionar al añadir **comparaciones** en la página Gastos. Esto le permite:

- Compare los valores actuales con una instantánea anterior del plan
- Resaltar los cambios a lo largo de las iteraciones de planificación
- Apoyar los debates sobre las variaciones durante las revisiones presupuestarias

## Restablecimiento del departamento a la versión anterior de la instantánea

Puedes restaurar una instantánea anterior y convertirla en la versión actual (más reciente) de los datos del plan de un departamento. Esto te permite recuperarte rápidamente de cambios no deseados y seguir planificando a partir de un momento concreto conocido y fiable.

Restaurar una instantánea como la última versión

Para restaurar una instantánea como la última versión, siga estos pasos:

1. En la vista «**Gastos** », acceda al **departamento de nivel inferior** deseado mediante el menú desplegable «**Departamentos** ».
2. En el menú desplegable **«Versión del plan»**, selecciona la **instantánea** que deseas restaurar como última versión.
3. En el cuadro de diálogo de confirmación **de «Restaurar instantánea»**, introduzca un **nombre para la instantánea**. Este nombre se utilizará para guardar una copia de la última versión actual antes de la restauración.
4. Pulse **Restaurar**.

**Resultado**

Cuando se lleva a cabo la operación de restauración:

- **La última versión** actual se guarda primero como una **nueva instantánea** con el nombre de instantánea proporcionado.
- A continuación, se borran los datos de la **última versión**.
- Los datos de la instantánea seleccionada se copian y se establecen como la nueva **versión más reciente**.

**Nota:** Esta operación no se puede realizar si el departamento **no** se encuentra en el estado «En curso».
