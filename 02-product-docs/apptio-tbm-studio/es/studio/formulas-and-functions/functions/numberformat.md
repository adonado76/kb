---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "NumberFormat función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/numberformat.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# NumberFormat función

Da formato a un valor numérico en una etiqueta (cadena) utilizando patrones personalizados para números positivos y negativos, duraciones o formato de tamaño de datos. Esta función está diseñada para su uso en columnas de tipo Etiqueta.

## Sintaxis

`NumberFormat(number, pattern, [options])`

## Parámetros

- número: El valor numérico a formatear. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio
- patrón: Cadena que especifica el formato para números positivos y, opcionalmente, para números negativos separados por punto y coma (por ejemplo, "#,###.#;(#,###.#)"). Opcional
- opciones: Argumentos con nombre opcionales que controlan el comportamiento adicional del formato. Entre las opciones admitidas se incluyen:
  - `compact`: Aplicar formato abreviado (consulte la sección Referencia de notación compacta para conocer los valores admitidos)
  - `negSymbol`: Utilice `dash`, `parens`, `none`, o `default` para ver los números negativos
  - `posColor`, `negColor`: Establece los colores de la fuente utilizando códigos hexadecimales HTML (por ejemplo, `#FF0000`)
  - `posBold`, `negBold`: Aplicar estilo negrita (`true`, `false`)
  - `posItalic`, `negItalic`: Aplicar estilo cursiva (`true`, `false`)
  - `posUnderline`, `negUnderline`: Aplicar estilo de subrayado (`true`, `false`)
  - `posPrefix`, `negPrefix`: Añadir HTML/texto antes del número
  - `posSuffix`, `negSuffix`: Añadir HTML/texto después del número Opcional

## Comportamiento

- Convierte una entrada numérica en una cadena formateada según el patrón o patrones proporcionados.
- Admite redondeos, símbolos monetarios, porcentajes, notación exponencial y abreviaturas byte/bit.
- Puede convertir duraciones (en segundos) en cadenas formateadas como '2 horas, 2 minutos'.
- Proporciona formato binario para tamaños de datos utilizando códigos como XA, XK, etc.
- Aplica el redondeo a la mitad: los valores que terminan en 1-4 se redondean hacia abajo, los que terminan en 5-9 se redondean hacia arriba.
- Cuando no se proporciona ningún patrón, los números se redondean a enteros y se muestran con comas.

## Ejemplos

`NumberFormat({Revenue}, "$#,##0.00")`: Formatea la columna {Revenue} como moneda con dos decimales, por ejemplo, "$1, 234.56 ".

`NumberFormat(7322, "s")`: Convierte 7322 segundos en una cadena de duración formateada: "2 horas, 2 minutos y 2 segundos".

`NumberFormat(922, "MB")`: Convierte 922 MB en una cadena legible como " 0.9 GB".

`NumberFormat(Percent, "00%")`: Formatea un porcentaje con dos dígitos, por ejemplo, 0.42 se convierte en "42%".

`NumberFormat($_, "#,###.#B", compact="XA")`: Formatea un valor de datos utilizando taquigrafía binaria, por ejemplo, " 1.0 GB".

`NumberFormat(-62619000.185, "#,###.#B;(#,###.##)")`: Forma el número negativo -62,619, 000.185 usando el patrón positivo `#,###.#B` y el patrón negativo `(#,###.##)`, resultando `(62,619,000.19)`.

`NumberFormat({NetIncome}, "$#,##0.00", compact="M", negColor="#FF0000",
posBold=true)`: Formatea la columna {NetIncome} como moneda en millones. Los números negativos aparecen en rojo y los positivos en negrita.

## Notas

- Utilice esta función sólo en columnas de tipo Etiqueta o en la fórmula de formato de columnas métricas/informes nuevos.
- El formato se ignora en las columnas numéricas.
- Si no se proporciona ni patrón ni negativePattern, los valores se redondean al entero más próximo con separador de miles.
- Cuando el formato incluya HTML, asegúrese de que las etiquetas prefijo/sufijo estén equilibradas y sean válidas.

## Referencia de notación compacta

Las tablas siguientes muestran los valores de notación compacta admitidos. En las tablas, la columna Código muestra los valores que puede poner después del parámetro opcional compact=. La columna Patrón para gráficos muestra las adiciones que puede poner al final del patrón de formato.

## Notaciones abreviadas estándar

Se admiten las siguientes notaciones abreviadas estándar. Los símbolos mostrados para cada formato abreviado estándar son específicos de cada país y pueden reconfigurarse en el cuadro de diálogo de configuración del proyecto. Así, por ejemplo, esta función de formato numérico utilizaría todas las notaciones abreviadas estándar:

=NumberFormat($\_, «#.#», compacto=A)

| Código | Patrón para gráficos | Descripción | Ejemplo |
| --- | --- | --- | --- |
| K | {@K} | Esto siempre resumirá los números en términos de "miles" | 100.000 aparece como 100K |
| M | {@M} | Esto siempre resumirá los números en términos de "millones" | 10.000.000 aparece como 10M |
| B | {@B} | Esto siempre resumirá los números en términos de "miles de millones" | 10.000.000.000 aparece como 10B |
| T | {@T} | Esto siempre resumirá las cifras en términos de "billones" | 10.000.000.000.000 aparece como 10T |
| A | {@A} | Esto resumirá los números utilizando todas las notaciones estándar. Para un número dado, se utilizará la notación de mayor orden de magnitud posible, de modo que el número visualizado sea mayor o igual que 1.0. Es decir, {@A} mostrará 964.999 como 9.65K no como 0.96M ya que 0.96 es menor que 1.0. En caso de duda, éste suele ser el mejor formato abreviado. | Todos los ejemplos anteriores son ciertos. |

## Notación abreviada binaria

También se admiten las siguientes notaciones abreviadas binarias:

Cuando utilice abreviaturas binarias, la mayoría de las veces estará resumiendo un número de bytes. En este caso, utilícela como declaración en NumberFormat :

=NumberFormat($\_, «#,###.#B», compacto=«XA»)

Del mismo modo, para mostrar esto en un gráfico, introduzca esto como Formato del número del gráfico: #, ###.#B{@Xa }

| Código | Patrón para gráficos | Descripción | Ejemplo |
| --- | --- | --- | --- |
| XK | {@XK} | Esto siempre resumirá los números en términos de "miles binarios" (dividir por 1024). | 1025 aparece como 1k |
| XM | {@XM} | Esto siempre resumirá los números en términos de "millones binarios" (dividir por 1024^2). | 1048577 aparece como 1M |
| XG | {@XG} | Esto siempre resumirá los números en términos de "miles de millones binarios" (dividir por 1024^3). | 1.073.741.825 aparece como 1G |
| XT | {@XT} | Esto siempre resumirá los números en términos de "trillones binarios" (dividir por 1024^4). | 1.099.511.627.777 aparece como 1T |
| XP | {@XP} | Esto siempre resumirá los números en términos de "cuatrillones binarios" (dividir por 1024^5). | 1.125.899.906.842.625 aparece como 1P |
| XE | {@XE} | Esto siempre resumirá los números en términos de "quintillones binarios" (dividir por 1024^6). | 1.152.921.504.606.846.977 aparece como 1e |
| XA | {@XA} | Esto resumirá los números utilizando todas las notaciones binarias. Para un número dado, se utilizará la notación de mayor orden de magnitud posible, de modo que el número visualizado sea mayor o igual que 1.0. En caso de duda, éste suele ser el mejor formato abreviado. | Todos los ejemplos anteriores son ciertos. |

## Tipo de retorno

Serie
