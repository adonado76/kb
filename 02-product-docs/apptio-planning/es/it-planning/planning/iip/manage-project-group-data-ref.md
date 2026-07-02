---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Gestionar los datos de referencia de los grupos de proyectos"
breadcrumb: []
source_path: "it-planning/planning/iip/manage-project-group-data-ref.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Gestionar los datos de referencia de los grupos de proyectos

Importante: *Disponible con la* *suscripción a* ***Apptio Planning Standard***

Los datos de referencia del grupo de proyectos representan la estructura jerárquica de proyectos o carteras de su organización.

1. En el menú de navegación, seleccione Datos de referencia > Dimensiones estándar > Grupo de proyectos.
2. Actualice los valores de la tabla de datos según sea necesario:
   - Código - Identificador único de un grupo de proyectos.
   - Nombre - Nombre del grupo de proyecto.
   - Código padre - Representa la jerarquía de su grupo de proyecto. El valor de un código padre es el valor del código de su cuenta inmediatamente superior o padre (si existe).
   - Código de moneda - La moneda común para el Grupo de Proyectos. Este valor es necesario cuando se habilita el soporte para múltiples monedas en el Perfil de la Empresa. El valor de la moneda común debe ser el código ISO de tres letras de la moneda. Si no se introduce ningún código de moneda, se utilizará la moneda común por defecto.
   - Código de Centro de Coste - El identificador de los Centros de Coste correspondientes. Cuando se importan reales, se asignan por Centro de Coste, y luego se asignan a Objeto de Coste o dimensiones dependientes. Un proyecto puede estar asociado a múltiples Centros de Coste y puede incluir partidas (volúmenes, mano de obra o gastos) registradas para más de un Centro de Coste. Añada múltiples Centros de Coste a la celda de la tabla utilizando una coma para separarlos.
