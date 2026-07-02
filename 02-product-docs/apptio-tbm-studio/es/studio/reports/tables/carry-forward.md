---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Traspaso"
breadcrumb: []
source_path: "studio/reports/tables/carry-forward.html"
images:
  - "resources/images/studio_images/cf-dataedit_463x489.png"
  - "resources/images/studio_images/cf-disable.png"
  - "resources/images/studio_images/cf-enable.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Traspaso

Esta función permite al usuario arrastrar los valores numéricos en un informe de tabla editable (ET).

Para activar esta función, vaya a la ventana emergente [Propiedades avanzadas](set-table-properties.htm "(se abre en una pestaña o una ventana nueva)").

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/cf-dataedit_463x489.png)

Seleccione la casilla de verificación **Editar datos** para activar la función de arrastre. El botón **Desactivar arrastre** aparece debajo del componente del informe.

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/cf-disable.png)

Nota: El arrastre sólo es aplicable para el valor numérico y las columnas consecutivas. Si hay una columna no numérica en medio, el arrastre no se aplicará a partir de entonces.

Si el usuario selecciona **Desactivar** arrastre, el arrastre se desactivará y el botón aparecerá como **Activar arrastre**.

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/cf-enable.png)

El comportamiento de arrastre sólo es aplicable a la sesión local y no persiste. Por lo tanto, cada vez que el usuario regrese, estará en el estado activado por defecto para el arrastre.
