---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Seleccione una opción de búsqueda"
breadcrumb: []
source_path: "studio/reports/select-search-option.html"
images:
  - "resources/images/studio_images/studioimages/reports/rep039.png"
  - "resources/images/studio_images/studioimages/reports/rep040.png"
  - "resources/images/studio_images/studioimages/reports/rep041.png"
  - "resources/images/studio_images/studioimages/reports/rep042.png"
  - "resources/images/studio_images/studioimages/reports/rep048.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Seleccione una opción de búsqueda

**Se aplica a** : TBM Studio 12.0 y posteriores

Si hay muchos valores en un slicer, los usuarios pueden limitar las entradas utilizando el cuadro de búsqueda automática situado en la parte superior del slicer. En la siguiente imagen, se ha introducido ABC y sólo se muestran los valores que empiezan por ABC. Cuando añades un slicer a un informe, puedes configurar cómo funcionará el cuadro de búsqueda automática.

![Cortador de identificación](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep048.png)

## Dos opciones de búsqueda

Hay dos opciones de búsqueda disponibles en la pestaña **Slicer**.

- **Contiene** - Busca todos los valores que incluyen los caracteres introducidos. Si el usuario escribe abc, el filtro encontrará abcefg, defabc y defabcefg, pero no abdc ni adbc.
- **Empieza por** - Busca todos los valores que empiezan por los caracteres introducidos. Si el usuario escribe abc, el filtro encontrará abcefg y abc, pero no dabc ni 1abc.

Seleccione la opción que considere que mejor se adapta a las necesidades de los usuarios. Los usuarios no pueden cambiar la opción de búsqueda cuando trabajan con la cortadora.

## Búsqueda jerárquica

La búsqueda jerárquica encuentra todos los valores que empiezan por el texto introducido más un carácter adicional. A continuación, crea una entrada de grupo para cada uno. La búsqueda jerárquica sólo puede aplicarse a las rebanadoras basadas en campos bloqueados en un objeto. Las rebanadoras jerárquicas se aplican a todos los componentes de un informe o, si están contenidas en un grupo, a todos los componentes del grupo, incluidas otras rebanadoras.

Para ilustrar cómo funciona una búsqueda jerárquica, suponga que tiene la tabla que se muestra en la siguiente imagen:

![Búsqueda jerárquica](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep039.png)

Se añade un slicer basado en el campo ID con una estrategia de búsqueda **Starts With** como se muestra en la siguiente imagen. El slicer contiene una entrada para cada coincidencia:

![ID Slicer y consulta Adhoc](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep040.png)

Si introduce el texto ABC en el campo de búsqueda y selecciona un valor como ABC100, obtendrá los resultados que se muestran en la siguiente imagen. Cada entrada de la cortadora representa un único valor de la tabla:

![Ejemplo](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep041.png)

Si cambia la estrategia de búsqueda a **Búsqueda por grupos**, obtendrá los resultados que se muestran en la Figura E a continuación. Tenga en cuenta que cada entrada de la rebanadora representa un grupo de valores. ABC1 cuando se selecciona, muestra los valores ABC100, ABC110, y ABC120:

![búsqueda de grupo](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep042.png)

Para crear una rebanadora jerárquica:

- Haga clic con el botón derecho en un campo bloqueado por objeto en una perspectiva personalizada y seleccione **Editar 'nombre'**.
- En el cuadro de diálogo **Editar campo publicado**, seleccione la opción **Representa un código de jerarquía**.
