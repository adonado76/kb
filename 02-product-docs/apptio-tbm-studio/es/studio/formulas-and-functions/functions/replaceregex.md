---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "ReplaceRegex función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/replaceregex.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# ReplaceRegex función

Realiza una sustitución basada en expresiones regulares de los valores de texto de una columna. Útil para extraer o limpiar datos mediante la concordancia avanzada de patrones.

## Sintaxis

`ReplaceRegex(column_name, match_expression, replacement_expression)`

## Argumentos

*nombre\_columna* : El nombre de la columna que contiene el texto a sustituir.

*expresión\_pareja* : La expresión regular que identificará el texto a reemplazar.

*expresión\_de\_reemplazo* : La expresión regular utilizada para crear el texto de reemplazo.

## Comportamiento

- Busca en cada fila de la columna especificada coincidencias con la expresión regular dada.
- Si se encuentra una coincidencia, el resultado se construye utilizando la expresión de sustitución, que puede incluir grupos de captura.
- Si no se encuentra ninguna coincidencia, se devuelve el valor original de la columna sin cambios. Utiliza la sintaxis de expresiones regulares de Java y admite coincidencias no ávidas mediante '?'.

## Tipo de retorno

Serie

## Ejemplo

Supongamos la siguiente sintaxis:

`ReplaceRegex([Source Column],[Regex Statement],[Capture Group])`

Si la sentencia regex encuentra una coincidencia en la columna de origen, la fórmula devolverá el valor del grupo de captura. Si no se encuentra ninguna coincidencia, devolverá el valor de la columna de origen. El tipo de regex compatible con la función es Java.

He aquí un ejemplo concreto:

```
=ReplaceRegex(Journal Entry
      Description,"^.*(INVOICE).{0,8}?(\d{10}).*","$2")
```

Esta fórmula buscará la palabra "FACTURA" (en mayúsculas) en la columna Descripción del asiento. Si encuentra esa cadena, devolverá el primer número de 10 dígitos que encuentre a menos de 8 caracteres del final de la palabra. Puede utilizar esta fórmula para analizar números de factura de 10 dígitos a partir de una descripción de asiento de texto libre. En este ejemplo, el primer grupo de captura ($1) es "FACTURA" y el segundo grupo de captura ($2) es el número de diez dígitos (\d {10} ).

He aquí un ejemplo de su resultado:

![](../../../resources/images/studio_images/studioimages/studio_diagram_output%20example.png)

Ahora, desglosemos lo que ocurre en la expresión regular de este ejemplo:

- El.\* final coincide con cualquier carácter, cualquier número de veces.
- De nuevo, el paréntesis especifica que este número es un grupo de captura. En este caso, su grupo de captura es el 2.
- 10} significa que la regla anterior debe aplicarse a 10 caracteres seguidos. Así, \d {10} significa "acertar 10 números seguidos"
- La \d significa hacer coincidir cualquier número.
- El signo de interrogación (?) significa que la coincidencia previa debe coincidir con el menor número de caracteres posible. Por ejemplo, si tiene un número de 11 dígitos, los 10 primeros dígitos coincidirán con el término siguiente, no los 10 últimos. Quitar el? coincidirá con los 10 últimos.
- El punto (.) significa lo mismo que antes. Sin embargo, la dirección {0,8} significa que puede coincidir con un mínimo de 0 y un máximo de 8 caracteres.
- El paréntesis que encierra la factura especifica que su valor debe ser capturado. El valor situado más a la izquierda entre paréntesis es el grupo de captura 1. Cada grupo de captura adicional incrementa el número en 1, de izquierda a derecha.
- La palabra "FACTURA" significa que coincide con la palabra exacta FACTURA. Se distingue entre mayúsculas y minúsculas.
- El asterisco (\*) significa que los criterios anteriores pueden coincidir con cualquier número de caracteres. Así, asterisco de punto (.\*) significa que coincide con cualquier número de cualquier carácter.
- El punto (.) es un comodín que coincide con cualquier carácter.
- El signo de intercalación (^) significa que nuestra expresión regular debe empezar a coincidir al principio del valor de la Descripción del asiento.

Observa la salida de la fila:

MI FACTURA PRINCIPAL ES 6872954678, PERO TAMBIÉN TENEMOS UNA FACTURA MAESTRA DE 1234567890

Esta salida corresponde al segundo número de factura, no al primero. Esto se debe al primer punto Asterisco (.\*) en la expresión regular. Este término emparejará tantos caracteres como pueda hasta que encuentre uno que no pueda emparejar. Si quisiéramos que coincidiera con el menor número de caracteres posible, podríamos añadir una? a nuestra expresión regular dando:

```
=ReplaceRegex(Journal Entry
      Description,"^.*?(INVOICE).{0,8}?(\d{10}).*","$2")
```

Para más información sobre la sintaxis regex o para probar sus propias sentencias regex, visite [http://www.rexegg.com/regex-quickstart.html](http://www.rexegg.com/regex-quickstart.html "(se abre en una pestaña o una ventana nueva)") y [regex101.com](https://regex101.com/ "(se abre en una pestaña o una ventana nueva)").

Nota:

- Para capturar partes específicas de la cadena coincidente, utilice paréntesis en la expresión de coincidencia y haga referencia a ellos como "\(1", "\)2", etc. en la expresión de sustitución.
- Si no se encuentra ninguna coincidencia en una fila, se devuelve el valor original de la columna.
- Asegúrese de probar sus patrones regex utilizando herramientas en línea o entornos basados en Java para garantizar la compatibilidad.
