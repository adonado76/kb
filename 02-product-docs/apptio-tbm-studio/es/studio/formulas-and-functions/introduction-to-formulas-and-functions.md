---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Introducción a las fórmulas y funciones"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/introduction-to-formulas-and-functions.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Introducción a las fórmulas y funciones

**Se aplica a** : TBM Studio 12.0 y posteriores

Puede utilizar fórmulas para insertar valores calculados en una columna de una tabla o en una métrica. Una función es un procedimiento predefinido que puede utilizarse en una fórmula para simplificar la codificación de cálculos complejos.

Utilizar fórmulas y funciones en:

- Los campos **Valor**, **Anulación de valor** y **Valores posibles** de una columna del conjunto de datos.
- Campo de **cálculo del valor** de una métrica.
- La barra de fórmulas de la cinta **Informe**.
- Una definición de controlador de unidad.

## Fórmulas

Una expresión es una combinación de símbolos y operadores que puede evaluarse para obtener un único valor de datos. Las expresiones simples pueden ser una única constante, variable, columna o función escalar. Los operadores pueden utilizarse para unir dos o más expresiones simples en una expresión compleja.

Una expresión puede incluir cualquiera de los siguientes elementos:

- Constantes
- Nombres de columna
- Fórmulas
- Funciones

Una expresión de cadena se evalúa como una cadena. Una expresión numérica se evalúa como un número. Una expresión de fecha se evalúa como una fecha. Muchas funciones toman expresiones como argumentos.

El formato de las fórmulas es

`=expression`

El siguiente ejemplo es una fórmula sencilla que multiplica el valor de la columna **Tarifa** por el valor de la columna **Tiempo**.

`=Rate*Time`

## Funciones

Una función es un procedimiento predefinido que inserta un valor en una tabla o modelo. El formato de las funciones es:

`=Function_Name(arguments)`

Los nombres de las funciones aparecen en MixedCase,, pero no distinguen entre mayúsculas y minúsculas. Los argumentos representan los datos de entrada que necesita la función. El siguiente ejemplo muestra una llamada a la función Max, con los argumentos requeridos, que en este caso son nombres de columnas. Esta función evalúa los valores de las columnas SalesEast y SalesWest y devuelve el mayor de los dos valores.

`=Max(SalesEast,SalesWest)`

Para una descripción detallada de todas las funciones, véase [Funciones - lista anotada](functions/functions.htm "(se abre en una pestaña o una ventana nueva)").

## Dónde pueden utilizarse las funciones

Las funciones pueden utilizarse en distintos lugares de TBM Studio:

- Conjuntos de datos
- Métricas calculadas e informes con columnas de métricas
- Columnas de fórmulas en tablas de informes
- Texto dinámico
- Fórmulas de origen de la asignación

Las descripciones de las funciones incluyen una lista de los lugares admitidos formalmente en los que se puede utilizar una función. Una función puede funcionar en otro lugar, pero su comportamiento será incoherente.
