---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Personalizaciones y cómo afectan a las actualizaciones de contenido"
breadcrumb:
  - "Costing Standard"
  - "Administración"
  - "Actualización de la norma de cálculo de costes"
source_path: "cost-transparency/admin/cust-contet.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Personalizaciones y cómo afectan a las actualizaciones de contenido

Si ha personalizado el contenido de IBM Apptio y actualiza un componente, el proceso de actualización no actualizará los elementos personalizados del componente. La actualización mantendrá intactos los elementos personalizados (no se aplicarán cambios) y actualizará cualquier elemento que no haya sido personalizado.

Por ejemplo, si ha modificado un conjunto de datos maestros y no ha realizado ninguna otra personalización, no obtendrá la nueva versión del conjunto de datos maestros al actualizar. Sin embargo, obtendrá otros informes, así como la actualización de los demás elementos de contenido relacionados con ese componente, como el conjunto de datos maestros y las métricas.

Si no ha personalizado el contenido de Apptio, el proceso de actualización sustituirá sus versiones de los mismos elementos de contenido por la última versión.

Tenga en cuenta que esto puede provocar un cambio en la funcionalidad.

## Personalizaciones

Las siguientes acciones se consideran personalizaciones de un proyecto, si se realizan en elementos predeterminados como tablas, informes y métricas.

- Eliminar una columna de un conjunto de datos maestros
- Cambiar un componente del informe
- Cambiar una métrica, perspectiva o campo publicado
- Cambiar el tipo de una columna de datos, por ejemplo, de numérico a etiqueta

## Configuraciones

Las siguientes acciones no se consideran una personalización del proyecto. Son configuraciones.

- Asignación de un conjunto de datos a un conjunto de datos maestro
- Cambiar la configuración de visibilidad de un conjunto de datos, como Ocultar del motor de inferencia
- Cambiar la configuración de categoría de un conjunto de datos

## Identificar personalizaciones

La sección Elementos personalizados de la página Detalles del componente identifica las personalizaciones entre su proyecto y la versión actual.

Haga clic en el signo más (+) junto a los elementos identificados para obtener más información sobre la personalización.
