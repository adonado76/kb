---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Gestionar los datos de referencia del proyecto"
breadcrumb: []
source_path: "it-planning/planning/iip/manage-project-data-ref.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Gestionar los datos de referencia del proyecto

Importante: *Disponible con la* *suscripción a* ***Apptio Planning Standard***

La siguiente información describe los campos de las dimensiones del proyecto.

1. En el menú de navegación, seleccione Datos de referencia > Cotas estándar > Proyecto.
2. Actualice los valores de la tabla de datos según sea necesario:
   - Código - Identificador único de un proyecto.
   - Nombre - Nombre del proyecto.
   - Código padre - Representa la jerarquía de su proyecto. El valor de un código padre es el valor del código de su cuenta inmediatamente superior o padre (si existe).
   - Permitir Cualquier Centro de Coste - Un valor de TRUE le permite asignar el proyecto a cualquier Centro de Coste. Un valor de FALSE toma por defecto el Centro de Coste actual.
   - Centro de costes por defecto - El valor por defecto, a menos que se proporcione un valor de código de centro de costes diferente.
   - Descripción - Resumen del proyecto.
   - Código de Centro de Coste - El identificador de los Centros de Coste correspondientes. Cuando se importan reales, se asignan por Centro de Coste, y luego se asignan a Objeto de Coste o dimensiones dependientes. Un proyecto puede estar asociado a múltiples Centros de Coste y puede incluir partidas (volúmenes, mano de obra o gastos) registradas para más de un Centro de Coste. Añada múltiples Centros de Coste a la celda de la tabla utilizando una coma para separarlos.
