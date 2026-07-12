---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Cortadoras jerárquicas"
breadcrumb: []
source_path: "studio/reports/hierarchical-slicers.html"
images:
  - "resources/images/studio_images/studioimages/reports/rep335.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Cortadoras jerárquicas

**Se aplica a** : TBM Studio 12.0 y posteriores

Utilizando un cortador jerárquico, los usuarios pueden profundizar en niveles de detalle cada vez mayores. Por ejemplo, en el slicer que se muestra en la siguiente imagen, un usuario puede seleccionar tipos de servidores. Las cortadoras jerárquicas pueden utilizarse en cortadoras compactas.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep335.png)

## Un cortador jerárquico se basa en un grupo

Un cortador jerárquico se basa en un grupo de perspectivas personalizado. El orden de las entradas en el grupo determina la jerarquía. Por ejemplo, el slicer que se muestra en la Figura A se creó utilizando un grupo de perspectivas personalizado con los siguientes campos: 01\_Type, 02\_SubType, 03\_OS. Se ha cambiado el nombre de los campos para crear el orden correcto.

## Crear una rebanadora jerárquica

1. En la pestaña **Informe**, haga clic en **Row Slicer**.
2. Cree la perspectiva personalizada que se utilizará en el slicer. Para más información, consulta [Crear perspectivas personalizadas](creating-custom-perspectives.htm "(se abre en una pestaña o una ventana nueva)").
3. En el área **Perspectivas** del **Explorador de proyectos**, haga clic con el botón derecho del ratón y cree un nuevo grupo.
4. Arrastre los campos al grupo recién creado.
5. Arrastre el grupo al área **Slice By** del diálogo.

## Ordenar los campos

Por defecto, los campos de una rebanadora jerárquica están en orden alfabético. Para cambiar el orden, cambie el nombre de los campos, añadiendo números secuenciales al principio de los nombres. Para cambiar el nombre de un campo, haga clic con el botón derecho en el campo y haga clic en **Editar**.

Nota: No puede utilizar guiones (-) en un nombre de campo. Sin embargo, puede utilizar dos puntos y guiones bajos.
