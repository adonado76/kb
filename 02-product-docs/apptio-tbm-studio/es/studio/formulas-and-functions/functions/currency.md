---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función de moneda"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/currency.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función de moneda

Formatea valores numéricos como cadenas monetarias, añadiendo el símbolo monetario apropiado en función de la configuración regional. Por defecto, los valores negativos se muestran en rojo.

## Sintaxis

`Currency(sourceColumn, [pattern], [options])`

## Argumentos

*columna fuente* : Una columna o expresión numérica que contiene los valores que deben formatearse como moneda. Encierre los nombres de las columnas entre llaves { }. Obligatorio

*patrón* : Una cadena opcional que especifica un patrón de formato personalizado. Opcional

*opciones* : Argumentos con nombre opcionales que controlan el comportamiento adicional del formato. Opcional

Opciones admitidas:

- `compact`: Aplicar formato abreviado (consulte la sección Referencia de notación compacta para conocer los valores admitidos)
- `negSymbol`: Utilice `dash`, `parens`, `none`, o `default` para ver los números negativos
- `minFractPrecision`: Número mínimo de dígitos después del punto decimal (número entero >= 0)
- `maxFractPrecision`: Número máximo de dígitos después del punto decimal (número entero >= 0)
- `localeprecisionoverride`: Anula los valores predeterminados de la configuración regional para la precisión decimal (`true`, `false`)
- `minIntPrecision`: Número mínimo de dígitos antes del punto decimal (número entero >= 0)
- `maxIntPrecision`: Número máximo de dígitos antes del punto decimal (número entero >= 0)
- `thousandSep`: Mostrar separador de miles (`true`, `false`, `default`)
- `posColor`: Establezca el color de la fuente para números positivos utilizando códigos hexadecimales HTML (por ejemplo, `#FF0000`)
- `negColor`: Establezca el color de la fuente para números negativos utilizando códigos hexadecimales HTML (por ejemplo, `#FF0000`)
- `posBold`: Aplique negrita a los números positivos (`true`, `false`, `default`)
- `negBold`: Aplique negrita a los números negativos (`true`, `false`, `default`)
- `posItalic`: Aplicar el estilo cursiva a los números positivos (`true`, `false`, `default`)
- `negItalic`: Aplicar el estilo cursiva a los números negativos (`true`, `false`, `default`)
- `posUnderline`: Aplicar el estilo de subrayado a los números positivos (`true`, `false`, `default`)
- `negUnderline`: Aplicar el estilo de subrayado a los números negativos (`true`, `false`, `default`)
- `posPrefix`: Añadir HTML/texto antes de números positivos
- `negPrefix`: Añadir HTML/texto antes de los números negativos
- `posSuffix`: Añadir HTML/texto después de números positivos
- `negSuffix`: Añadir HTML/texto después de números negativos

## Comportamiento

- Añade al valor numérico un símbolo de moneda adecuado a la configuración regional actual.
- Formatea el número de acuerdo con el patrón especificado si se proporciona.
- Aplica opciones de estilo opcionales como color, negrita, cursiva y formatos numéricos compactos.
- Muestra los valores negativos en rojo por defecto a menos que se anulen con opciones.

## Ejemplos

Moneda( {Cost} ): Formatea los valores de la columna {Cost} como moneda basada en la configuración regional, mostrando los números negativos en rojo.

Currency( {Revenue}, "#,## 0.00 ¤"): Formatea {Revenue} con un patrón personalizado, asegurando dos decimales y un símbolo de moneda.

Currency( {Profit}, "#,##0", compact="K", posColor="green", negColor="red" ): Formatea {Profit} utilizando notación compacta (por ejemplo, 1.000 → 1K ), mostrando los números positivos en verde y los negativos en rojo.

Nota:

- Las mejores prácticas recomiendan convertir todos los valores financieros a una moneda común antes de utilizarlos en controladores o informes.
- Los parámetros "patrón" y "opciones" permiten ajustar la salida a las distintas necesidades de estilo y elaboración de informes.
- El uso de 'compact=A' selecciona automáticamente la mejor unidad para números grandes (por ejemplo, K, M, B, T).
- Las opciones de color y estilo de fuente ayudan a personalizar el aspecto de los números positivos y negativos de forma independiente.

## Referencia de notación compacta

Se admiten las siguientes notaciones abreviadas estándar. En esta tabla, la columna Código son los valores que puede poner después del parámetro opcional compact=. La columna Patrón para gráficos muestra las adiciones que puede poner al final del patrón de formato para dar formato a un gráfico:

**Notaciones abreviadas estándar**

| Código | Patrón para gráficos | Descripción | Ejemplo |
| --- | --- | --- | --- |
| K | {@K} | Esto siempre resumirá los números en términos de "miles" | 100.000 aparece como 100K |
| M | {@M} | Esto siempre resumirá los números en términos de "millones" | 10.000.000 aparece como 10M |
| B | {@B} | Esto siempre resumirá los números en términos de "miles de millones" | 10.000.000.000 aparece como 10B |
| T | {@T} | Esto siempre resumirá los números en términos de "billones" | 10.000.000.000.000 aparece como 10T |
| A | {@A} | Esto resumirá los números utilizando todas las notaciones estándar. Para un número dado se utilizará la notación de orden de magnitud más alta posible, de forma que el número visualizado sea mayor o igual que 1.0. IE, {@A} mostrará 964,999 como 9.65K no como 0.96M ya que 0.96 es menor que 1.0. En caso de duda, éste suele ser el mejor formato abreviado. | Todos los ejemplos anteriores son ciertos. |
