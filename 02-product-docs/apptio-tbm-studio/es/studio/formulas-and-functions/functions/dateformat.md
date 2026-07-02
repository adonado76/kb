---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "DateFormat función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/dateformat.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# DateFormat función

Convierte una expresión de fecha a un formato de fecha especificado.

## Sintaxis

```
DateFormat(date_expression, format_string [, time_zone [, from_format]])
```

## Parámetros

- *expresión\_fecha* : El valor de la fecha a formatear. Puede ser una Fecha o una Cadena. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio
- *cadena\_formato* : Especifica el formato deseado de la cadena de salida. Utiliza patrones de formato de fecha estándar (por ejemplo, 'aaaa-MM-dd'). Consulte la sección Referencia de patrones más abajo para obtener una lista completa de las letras de patrones disponibles. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio
- *zona\_horaria* : Especifica la zona horaria para mostrar la fecha y la hora. Para incluir la zona horaria en la salida, la cadena format\_string debe incluir una 'z'. Opcional (por defecto: GMT)
- *from\_format* : Especifica el formato actual de la expresión\_fecha si es una Cadena. Se utiliza para analizar correctamente la fecha antes de formatearla. Utiliza las mismas letras de patrón que format\_string - véase la sección Referencia de patrones más abajo. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Opcional (por defecto: análisis sintáctico por defecto dependiente de la configuración regional)

## Ejemplos

Los siguientes ejemplos suponen una fecha del 12 de octubre de 2014 10:24:52 AM.

- Formatea la fecha actual como 'año-mes-día'. `DateFormat(CurrentDate(),
  "yyyy-MM-dd")`
- Analiza la fecha y hora ISO de entrada, la cambia a la hora del Pacífico y la formatea como 'Apr 29, 2025'.

  ```
  DateFormat("2025-04-29T08:00:00", "MMM dd, yyyy", "PST", "yyyy-MM-dd'T'HH:mm:ss")
  ```

Nota: Cuando se utiliza time\_zone, la cadena format\_string debe incluir 'z' para mostrar realmente la zona horaria en el resultado. Si se omite from\_format y date\_expression es una cadena, el análisis sintáctico puede fallar si el formato no coincide con las suposiciones predeterminadas del sistema.

## **Referencia del patrón de fecha y hora**

Los formatos de fecha y hora se definen mediante cadenas de patrones. En estas cadenas, las letras no entrecomilladas de 'A'-'Z' y 'a'-'z' sirven como símbolos de patrón que representan partes de la fecha o la hora. Para incluir texto literal, puede utilizar comillas simples ('); dos comillas simples consecutivas ('') representan una comilla simple literal. El resto de caracteres se tratan como literales, es decir, se insertan en la salida formateada o se ajustan exactamente durante el análisis sintáctico. La siguiente tabla muestra las letras de patrón que pueden utilizarse en format\_string y from\_format:

| Elemento de formato | Formato | Descripción | Ejemplo |
| --- | --- | --- | --- |
| M | MMMMMMMMMM | Mes | M: 6MM: 06MMM: JunMMMMM: Junio |
| D | DDDDDD | Día del año. El número de D determina el número de dígitos visualizados | D: 7 (7 de enero)DD: 07 (7 de enero)DDD: 007 (7 de enero) |
| d | ddd | Día del mes (del 1 al 31) | d: 2dd: 02 |
| w | www | La semana del año (1 a 52) | w: 9ww: 09 |
| W | W | Semana del mes en que se produce la fecha (1 a 5) | 1 |
| E | E | Día de la semana | Lun |
| E | EEEE | Día de la semana (largo) | Lunes |
| F | F | Día de la semana en el mes (el número de veces que se ha producido el día de la semana durante el mes) | 2 |
| y | yyyyyy | Año | yy: 14yyyy: 2014 |
| H | HHH | Hora en hora militar (0-23) | H: 4, 14HH: 04, 14 |
| h | hhh | Hora en am/pm (1-12) | h: 2hh: 02 |
| m | mmm | Minuto (0-59) | m: 3, 30mm: 03, 30 |
| s | sss | Segundo en minutos (0-59) | s: 3, 30ss: 03, 30 |
| S | SSSSSS | Milisegundo | S: 7SS: 07SSS: 007 |
| a |  | Mostrar AM o PM según corresponda | AM |
| z | z | Huso horario general (formato corto) | GMT |
| z | zzzz | Huso horario general (formato largo) | Hora de Greenwich |
| Z | Z | RFC822 zona horaria (desfase con respecto a GMT) | 8 (para la hora del Pacífico) |
| p | ppp | Descripción a corto plazo | Tipos de calendario de periodos: P1Gregorian tipo de calendario: Mar |
| p | pppp | Descripción a largo plazo | Tipos de calendario de periodos: Período 1Gregorian tipo de calendario: Marzo |
| f | ffff | Período año fiscal | FY2014 |

## Tipo de retorno

Serie
