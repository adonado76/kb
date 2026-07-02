---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "EvalWiki función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/evalwiki.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# EvalWiki función

**Se aplica a** : TBM Studio 12.0 y posteriores

La función EvalWiki se utiliza para evaluar los enlaces wiki y el texto dinámico y formatearlo para su visualización en un informe. Esta función sólo puede utilizarse en los informes. No puede utilizarse en conjuntos de datos. Para más información sobre el uso de enlaces Wiki, véase Codificación de enlaces a otros informes en la Guía del usuario.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Columnas de fórmulas en tablas de informes
- Texto dinámico

## Sintaxis

`EvalWiki(wikitext)`

## Argumentos

*wikitexto*

Una cadena de texto Wiki.

## Ejemplo 1: Utilización de texto dinámico en varios informes

Suponga que tiene un gran bloque de texto que desea mantener en un lugar del sistema y colocarlo en varias páginas de informes. Esto puede hacerse utilizando EvalWiki. Haga un conjunto de datos de una fila (e. g.: TextBlocks ) con una columna llamada Texto. Introduzca el bloque de texto en la celda de la tabla.

En un informe, añada un componente HTML que incluya <%=EvalWiki(TextBlocks:Text )%>. Esto evaluará los enlaces wiki y el texto dinámico en ese valor. No es posible obtener el valor mediante una búsqueda normal.

## Ejemplo 2: Añadir enlaces a las celdas de una tabla

Supongamos que desea tener varias columnas en una tabla de un informe, y en esas columnas desea enlaces que lleven al usuario a diferentes lugares. Esto puede hacerse utilizando EvalWiki:

1. En TBM Studio, inserte una nueva columna en la tabla.
2. En el cuadro de diálogo **Editar columna**, marque la opción **Forzar etiqueta**.
3. Introduzca una fórmula como la siguiente:

   ```
   =EvalWiki("[[/myObject/!FILTER[myColumn="""&myColumn&"""]/ myReport|click here
                 to see my report]]")
   ```

Esto creará un enlace que navegará a un informe de objeto filtrado en el objeto myObject. Filtrará para mostrar sólo las filas en las que myColumn en ese informe de objetos sea igual al valor de myColumn en la tabla actual.
