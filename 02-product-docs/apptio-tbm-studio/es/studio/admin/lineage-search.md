---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Búsqueda de linaje"
breadcrumb: []
source_path: "studio/admin/lineage-search.html"
images:
  - "resources/images/studio_images/filter-lineage-1.png"
  - "resources/images/studio_images/filter-lineage-2.png"
  - "resources/images/studio_images/filter-lineage.png"
  - "resources/images/studio_images/lsearch-1.png"
  - "resources/images/studio_images/lsearch-2.png"
  - "resources/images/studio_images/lsearch-3.png"
  - "resources/images/studio_images/lsearch-4.png"
  - "resources/images/studio_images/lsearch-5.png"
  - "resources/images/studio_images/lsearch-6.png"
  - "resources/images/studio_images/lsearch-7.png"
  - "resources/images/studio_images/multiple-search.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Búsqueda de linaje

La búsqueda de linaje permite al usuario buscar en el complejo gráfico de linaje una entidad que coincida con el término de búsqueda.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/filter-lineage.png)

Incluso en un diagrama de linaje relativamente pequeño como éste, puede ser difícil, de un vistazo, saber qué son todas las entidades. Esto es especialmente cierto para subtipos como columnas o dimensiones, que se representan como iconos en lugar de cuadros completos con nombres. Aquí es donde entra en juego la búsqueda. Por ejemplo, si escribe "unidad" (la búsqueda no distingue entre mayúsculas y minúsculas), aparecerán todas las entidades que coincidan con la consulta de búsqueda:

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/filter-lineage-1.png)

Y desvanecer las entidades que no coincidan con la consulta de búsqueda

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/filter-lineage-2.png)

Los términos de búsqueda múltiples separados por un espacio se tratan como un OR implícito, por ejemplo, una entidad se resaltará si coincide con cualquiera de los términos de búsqueda

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/multiple-search.png)

## Filtro

Además de resaltar las entidades que coinciden con las consultas de búsqueda, los resultados también se pueden utilizar para filtrar el gráfico hacia abajo para las solicitudes posteriores. Para ello se utilizan los tres botones situados a la derecha de la barra de búsqueda :

- Añadir coincidencia
- Ocultar No coincidentes
- Ocultar coincidencia

## Añadir coincidencia

Haga clic en el botón Añadir coincidencia (signo más verde)

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/lsearch-5.png)

Esto generará un nuevo diagrama de linaje en el que todas las entidades que anteriormente coincidían con la consulta de búsqueda se han añadido a la sección "Claves añadidas". Aunque esto puede no tener un efecto inmediatamente obvio en el diagrama, significa que estas entidades persistirán en consultas posteriores, incluso si su subtipo general está oculto. Esto es muy útil cuando se quiere encontrar una entidad específica, como una columna o una dimensión, de la que se quiere trazar el linaje, incluso si no se está realmente interesado en ese tipo de entidad o se desea excluirlas para facilitar la lectura.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/lsearch-6.png) ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/lsearch-7.png)

## Ocultar No coincidentes

Para ocultar las entidades del diagrama que no coincidan con la consulta "Unidades ETC", seleccione el icono Ocultar no coincidentes (menos rojo).

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/lsearch-4.png)

Se emite una nueva consulta de linaje, en la que todas las entidades que se habían desvanecido anteriormente quedan ocultas del diagrama y de todas las consultas de linaje posteriores

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/lsearch-3.png)

## Ocultar coincidencia

Para ocultar entidades del diagrama que coincidan con la consulta "Unidades ETC", seleccione el icono de la derecha **Ocultar coincidencias** (menos verde)

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/lsearch-2.png)

Esto generará un nuevo diagrama de linaje en el que todas las entidades que anteriormente coincidían con la consulta de búsqueda se han añadido a la sección "Claves ocultas", ocultándolas eficazmente del diagrama y de todas las consultas de linaje posteriores. Esto puede ser útil para filtrar rápidamente resultados espurios o rutas de ramificación que no le interese rastrear:

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/lsearch-1.png)
