---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función plural"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/plural.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu689.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función plural

devuelve la forma plural de un sustantivo singular dado basándose en un recuento. Esto resulta útil para generar dinámicamente etiquetas o cadenas de visualización gramaticalmente correctas.

## Sintaxis

`Plural(noun,count)`

## Argumentos

*sustantivo* : La forma singular de un sustantivo a pluralizar (por ejemplo, "servidor", "centro de datos"). Se admiten sustantivos compuestos y frases de varias palabras. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio

*recuento* : Expresión numérica utilizada para determinar si se debe pluralizar el sustantivo. Si el valor es superior a 1, el sustantivo se pluraliza. Si se omite, el sustantivo siempre se pluraliza. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Opcional

## Tipo de retorno

Serie

## Ejemplo

![ejemplo de función plural](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu689.png)

- `Plural("server", 2)`: Devuelve "servidores" porque el recuento es mayor que uno.
- `Plural("network", {Network Count})`: Devuelve "red" o "redes" en función del valor de {NetworkCount}.
- `Plural("operating system")`: Devuelve "sistemas operativos" ya que no se especifica ningún recuento (siempre en plural).

Nota:

- Esta función no convierte automáticamente la salida a minúsculas. Para ello, envuélvalo en la función Lower (por ejemplo, Lower(Plural(...))).
- Se utiliza mejor en columnas de tipo etiqueta o expresiones de salida formateadas en las que importa la precisión gramatical.
- No se admiten los sustantivos irregulares; se aplican las reglas de pluralización estándar.
