---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Sintaxis de fórmulas y funciones"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/syntax-for-formulas-and-functions.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Sintaxis de fórmulas y funciones

**Se aplica a** : TBM Studio 12.0 y posteriores

Además de las convenciones sintácticas básicas para el código de fórmulas y funciones, la sintaxis de funciones incluye reglas para:

- **Búsqueda de datos** - Referencia a la tabla actual (búsqueda interna) y a otras tablas (búsqueda externa).
- **Referencia a nombres de columna** - Cuando se hace referencia a nombres de columna, la mejor práctica es encerrar los nombres de columna entre llaves, y esto es necesario cuando los nombres de columna contienen caracteres especiales.
- **Operadores** - Se admiten operadores estándar, así como operadores de rollup, que hacen referencia a las unidades de origen o destino de un rollup de datos.
- **Concatenación** de cadenas: puede dar formato a las fórmulas para incluir cadenas combinadas, como unidades de medida, con valores calculados.

## Convenciones sintácticas

La información que figura a continuación emplea las siguientes convenciones para describir la sintaxis de las funciones.

- **Monospace** - Este documento presenta toda la sintaxis de las funciones en monospace.
- **MixedCase monospace** - Los nombres de las funciones se muestran en MixedCase,, pero no se distingue entre mayúsculas y minúsculas.
- **[ ] (corchetes)** - Elementos opcionales. (No escriba los corchetes.)
- **,...n** - Indica que el argumento precedente puede repetirse cualquier número de veces, separadas por comas.

## Espacios

No ponga espacios en las fórmulas, excepto como parte de una cadena entrecomillada o según sea necesario en los nombres de columna. En este documento, las especificaciones de sintaxis pueden incluir espacios para mejorar la legibilidad, pero todos los ejemplos se dan sin espacios. La sintaxis de estos documentos de ayuda emplea fuentes monoespaciadas y espacios para mejorar la legibilidad. Sin embargo, no deben utilizarse espacios al escribir fórmulas y funciones en la aplicación.

## Cuerdas

Encierra todas las cadenas entre comillas dobles ( " " ).

Por ejemplo:

"Costes totales para el año 2009"

Los nombres de columna no se consideran cadenas y no tienen que ir entre comillas dobles.

Para escapar de un símbolo de comillas, utilice comillas dobles ("" "").

## Valores de retorno nulos

Las funciones que se resuelven en 0 o en null se muestran como 0 en el campo.
