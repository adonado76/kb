---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función de valor"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/value.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función de valor

Convierte una cadena de aspecto numérico en un número utilizando un patrón de formato opcional. Útil para extraer valores numéricos de cadenas que incluyen texto o símbolos.

## Sintaxis

`Value(value, pattern)`

## Parámetros

*valor* : La expresión de cadena a convertir en número. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio

*patrón* : Opcional. Patrón utilizado para comparar y analizar el valor numérico. Puede ser un patrón sufijo (por ejemplo, "#GB") o un patrón numérico completo como el utilizado en NumberFormat. Si se omite, la función intentará deducir el formato correcto. Opcional

Patrón utilizado para la concordancia. El patrón puede ser cualquiera:

- Un sufijo que indica que el análisis sintáctico debe tomar el número hasta el primer carácter no numérico.
- Un patrón numérico completo reconocible por [NumberFormat](numberformat.html "Da formato a un valor numérico en una etiqueta (cadena) utilizando patrones personalizados para números positivos y negativos, duraciones o formato de tamaño de datos. Esta función está diseñada para su uso en columnas de tipo Etiqueta.").

Si no se especifica *un patrón*, la función hace una estimación e intenta analizar el *valor* utilizando uno de los formatos numéricos predeterminados.

## Tipo de retorno

Número

## Ejemplo

El siguiente ejemplo evalúa la cadena de la columna Almacenamiento y devuelve la parte numérica de la cadena hasta los caracteres GB. Si Almacenamiento contiene la cadena 57GB, este ejemplo devuelve 57. : `=Value(Storage,"#GB")`

`Value("$1,234.56")`: Analiza la cadena y devuelve el valor numérico 1234.56.

Nota: Si falla el análisis sintáctico, la función devuelve null.
