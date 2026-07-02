---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función meses"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/months.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función meses

Convierte una fecha especificada en un valor decimal que representa el número de períodos desde el 1 de enero de 1970. Útil para cálculos basados en el tiempo, como la determinación de duraciones o el prorrateo de costes.

## Sintaxis

`Months(date_expression, format)`

## Argumentos

- *expresión\_fecha* : Una expresión que evalúa a una fecha que debe convertirse a un valor doble. El formato es: "MM/DD/AAAA HH:MM" o cualquier otro formato de fecha estándar soportado por la aplicación. La expresión puede ser el nombre de una columna.
- *formato* : Un literal de cadena que especifica el formato de la fecha (por ejemplo, "MM/dd/aaaa"). Opcional si el formato de fecha es autodetectable. Opcional

## Comportamiento

- Devuelve el número de periodos (meses) desde el 1 de enero de 1970 como número decimal.
- Los periodos parciales se incluyen como valores fraccionarios. Por ejemplo, 1.1 representa un mes completo y parte de otro.
- Puede utilizarse en fórmulas para calcular duraciones, asignar costes o comparar plazos.

## Tipo de retorno

Número

## Ejemplo

- `Months("01/01/1970")`: Devuelve 1 porque es la fecha de referencia.
- `Months("01/02/1970")`: Devuelve 1.032.
- `Months({ProjectEnd}) - Months({ProjectStart})`: Calcula la duración en meses entre dos fechas de proyecto.
- `(Months({ProjectEnd}) - Months({ProjectStart}))*` Multiplica el número de meses entre las fechas de inicio y fin por el coste mensual del proyecto para estimar el coste total.

Nota:

- El resultado incluye meses parciales como valores decimales, lo que lo hace adecuado para cálculos prorrateados.
- El formato de fecha sólo es necesario si la plataforma no puede procesar automáticamente la fecha introducida.
- La función se basa en el 1 de enero de 1970 como referencia de época.
