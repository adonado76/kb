---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Borrar una tabla editable"
breadcrumb: []
source_path: "studio/reports/tables/delete-table.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Borrar una tabla editable

1. Echa un vistazo a la tabla editable.
2. En la pestaña **Inicio** del grupo **Documento**, haga clic en **Eliminar**.
3. Comprobar en la tabla editable.

Estas tablas no pueden recuperarse posteriormente mediante la restauración del registro de auditoría. Para advertir al usuario de esta consecuencia, aparece un mensaje de advertencia como el que se muestra.

![Confirmar supresión](../../../resources/images/studio_images/r-notes/purge%20sql%202_582x354.png)

Debe eliminar todas las dependencias antes de eliminar la tabla editable, ya que no estará disponible ninguna tabla de base de datos de respaldo. Si un elemento editable tiene elementos dependientes (excepto informes), el botón de confirmación de eliminación se desactivará y aparecerá un mensaje de error como el que se muestra.

![Confirmar la opción Suprimir](../../../resources/images/studio_images/r-notes/purge%20sql%201_576x404.png)
