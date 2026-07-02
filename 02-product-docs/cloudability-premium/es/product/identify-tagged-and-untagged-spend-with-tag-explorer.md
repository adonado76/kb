---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Identificar los gastos etiquetados y no etiquetados con Tag Explorer"
breadcrumb:
  - "Cloudability Premium"
  - "Detalles"
source_path: "product/identify-tagged-and-untagged-spend-with-tag-explorer.html"
images:
  - "images/tag_explorer_mceclip0.jpg"
  - "images/tag_explorer_not_set-drilldown.jpg"
  - "images/tag_explorer_service.jpg"
  - "images/tag_explorer_untaggable.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Identificar los gastos etiquetados y no etiquetados con Tag Explorer

Con Tag Explorer, le facilitamos la tarea de ver qué etiquetas utiliza actualmente su organización. Por ejemplo, si sabe que su empresa utiliza la etiqueta Equipo para asignar gastos, pero no recuerda si los valores del equipo deben ser minúsculas, mayúsculas, espacios, abreviaturas, etc, Tag Explorer está aquí para ayudarle.

![captura de pantalla del explorador de etiquetas](../../../../03-media/cloudability-premium/images/tag_explorer_mceclip0.jpg)

El escenario

Muchos clientes utilizan Tag Explorer para la gestión de activos. Continuando con el ejemplo anterior, si desea identificar qué recursos carecen actualmente de etiquetas de Equipo, sólo debe hacer clic en el segmento No configurado para Equipo para mostrar esos recursos en la tabla siguiente.

![captura de pantalla del explorador de etiquetas](../../../../03-media/cloudability-premium/images/tag_explorer_not_set-drilldown.jpg)

Para los clientes que ejecutan infraestructuras en varias nubes públicas, ofrecemos una forma sencilla de ver el uso de etiquetas en un único panel. En este ejemplo, utilizamos la etiqueta «Service» para identificar un proceso que se ejecuta en paralelo en Azure, GCP y AWS.

![captura de pantalla de los servicios del explorador de etiquetas](../../../../03-media/cloudability-premium/images/tag_explorer_service.jpg)

No todos los recursos de AWS admiten el etiquetado. En la pestaña Gastos no etiquetados, puede ver una interfaz sencilla para visualizar todos los recursos de AWS que actualmente no admiten etiquetas. Tenga en cuenta que los Grupos de cuentas y las Dimensiones de negocio no se enfrentan a restricciones comparables, por lo que no se muestran en esta vista.

![Explorador de etiquetas sin etiquetar Captura de pantalla de Sepnd](../../../../03-media/cloudability-premium/images/tag_explorer_untaggable.jpg)

La solución

Para repasar, Cloudability ofrece una variedad de etiquetas para reunir tus recursos en la nube en grupos significativos.

- Las etiquetas mapeadas ofrecen una forma sencilla de introducir las etiquetas existentes en Cloudability con la opción de combinar etiquetas duplicadas en una sola dimensión. Esto incluye las etiquetas de AWS, las etiquetas de recursos y las etiquetas de proyectos de GCP, así como las etiquetas y los grupos de recursos de Azure.
- Los grupos de cuentas le permiten aplicar etiquetas a nivel de cuenta, que luego fluyen a través de cualquier recurso que sea consumido por esa cuenta. Desde el punto de vista funcional, son muy similares a las etiquetas de proyecto de GCP.
- Business Dimensions le permite aplicar etiquetas utilizando reglas arbitrarias que usted define.

Preguntas más frecuentes

- ¿Cuántas etiquetas se muestran?

  En esta visualización se muestran las quince etiquetas más utilizadas. Tenga en cuenta que se excluyen las etiquetas con una cobertura inferior al 1%. Para esta visualización, las etiquetas con un gasto mínimo se agrupan en un cajón de sastre denominado "Otros". No es un valor de etiqueta real en sus datos, y puede ver qué valores de etiqueta individuales se están agregando en "Otros" seleccionando el segmento "Otros".
- ¿Permite Tag Explorer ver los diferentes tipos de etiquetas (etiquetas de grupos de recursos, etiquetas de suscripciones, etiquetas de « GCP » y etiquetas, etc.)?

  Sí. Tag Explorer ofrece información sobre las etiquetas de los grupos de recursos, las etiquetas de las cuentas y suscripciones, las etiquetas y las etiquetas de « GCP », así como las etiquetas de los recursos.
