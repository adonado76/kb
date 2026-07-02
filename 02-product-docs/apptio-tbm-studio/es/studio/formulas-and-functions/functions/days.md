---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función días"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/days.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu126.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función días

Convierte una fecha especificada en un valor numérico que representa el número de días transcurridos desde el 1 de enero de 1970.

Convierte una fecha especificada en un valor decimal, que puede utilizarse en fórmulas. El valor decimal es el número de días transcurridos desde el 1 de enero de 1970.

## Sintaxis

`Days(date_expression [, from_format])`

## Parámetros

*fecha\_expresión*

Expresión que evalúa una fecha para convertirla en un valor numérico. La expresión debe representar sólo una fecha y no puede incluir un componente temporal. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio

## Comportamiento

- Convierte la fecha proporcionada en el número de días transcurridos desde el 1 de enero de 1970.
- Si se especifica from\_format, la función lo utiliza para analizar la cadena de fecha de entrada.
- Si la expresión\_fecha incluye un componente temporal, debe ignorarse o truncarse.

## Tipo de retorno

Número

## Ejemplo

El siguiente ejemplo calcula la duración del proyecto en días y la multiplica por el coste diario del proyecto.

`=(Days(ProjectEnd)-Days(ProjectStart))*ProjectCostPerDay`

Nota: Sólo se admiten valores de fecha (sin hora). Si se omite from\_format y la expresión date\_expression es una cadena, el sistema intentará analizarla según la configuración regional predeterminada.

## Convertir días en una marca de tiempo UNIX

Una marca de tiempo UNIX es el número de segundos que han transcurrido desde el 1 de enero de 1970. Este número puede ser útil si quieres hacer cuentas con fechas. Puede convertir el resultado de la función Días en una marca de tiempo UNIX utilizando la siguiente fórmula:

`=Days(date_expression)*24*60*60`

Toma el resultado de la función Días y lo multiplica por el número de segundos de un día: 24 horas x 60 minutos x 60 segundos.

Por ejemplo, puedes convertir las fechas que aparecen en la siguiente tabla:

![imagen](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu126.png)

La fórmula de la columna Función Días es: =Días(Fecha)

La fórmula para la columna UNIX Time Stamp es: =(Función Días)\*24\*60\*60

Consulte también:

- [CurrentDate](currentdate.html "Devuelve la fecha de inicio del periodo de tiempo actualmente seleccionado, si el tiempo está activado. Si no, devuelve Eon 2000.")
- [Horas](hours.html "Convierte un valor de fecha en el número de horas transcurridas desde el 1 de enero de 1970, como valor numérico.")
- [Minutos](minutes.html "Convierte un valor de fecha en el número de minutos transcurridos desde el 1 de enero de 1970, como valor numérico.")
- [Meses](months.html "Convierte una fecha especificada en un valor decimal que representa el número de períodos desde el 1 de enero de 1970. Útil para cálculos basados en el tiempo, como la determinación de duraciones o el prorrateo de costes.")
