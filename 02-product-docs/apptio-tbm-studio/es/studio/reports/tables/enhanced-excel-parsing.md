---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Cómo funciona el análisis sintáctico mejorado de Excel en Apptio"
breadcrumb: []
source_path: "studio/reports/tables/enhanced-excel-parsing.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Cómo funciona el análisis sintáctico mejorado de Excel en Apptio

Nota: A partir de la versión 12.11.16, la función Enhanced Excel Parsing se activa automáticamente para los nuevos clientes. Actualmente no hay cambios para los clientes existentes. En próximas actualizaciones se ofrecerá más información.

## Qué esperar al cargar archivos

Al cargar archivos en Apptio, puede esperar lo siguiente:

- El archivo se analizará y los datos se extraerán sin procesar, sin ningún formato aplicado en Excel.
- Los datos de la tabla de transformación se rellenarán según los valores brutos definidos en la especificación Apptio.
- Si hay algún problema con los pasos de transformación de la tabla o necesita datos en un formato específico, consulte el documento de ayuda para aplicar el formato correcto.
- Si el archivo Excel contiene algún formato especial o macros, es posible que no se cargue correctamente y que sea necesario aplicar el formato como parte de los pasos de transformación de la tabla.

**Consejos para solucionar problemas**

Si tiene algún problema con los pasos de transformación, intente lo siguiente:

- Compruebe los pasos de transformación de la tabla y corrija el formateador si los datos no están en el formato solicitado.
- Compruebe que el archivo no contiene ningún formato especial ni macros.
- Póngase en contacto con nuestro equipo de asistencia para obtener ayuda.

Ventajas de pasar al nuevo analizador de hojas de cálculo.

- **Formato normalizado de los datos de Excel:** El nuevo analizador sintáctico establece un formato coherente para los datos de Excel.
- **Precisión numérica mejorada:** Lee directamente los valores numéricos sin procesar, omitiendo cualquier formato que pudiera alterar los datos originales, lo que da lugar a cálculos más precisos.
- **Representación coherente de fecha y hora:** Todos los valores de fecha y hora se convierten a formato de época, eliminando la necesidad de conversiones complejas y propensas a errores.

## Preguntas frecuentes

P: **¿Qué formatos de hoja de cálculo admite Apptio?**

R: Apptio admite XLSX, XLS

P: **¿Qué ocurre si tengo problemas para cargar o procesar archivos Excel?**

R: Póngase en contacto con nuestro equipo de asistencia para obtener ayuda.

## ¿Qué cambia con el nuevo excel parser frente al antiguo?

|  |  |  |  |
| --- | --- | --- | --- |
| Formatos | Analizador sintáctico actual de hojas de cálculo | Nuevo analizador sintáctico de hojas de cálculo | Funciones para convertir del nuevo formato del analizador sintáctico al formato antiguo |
| Tema general | Hola | Hola | No es necesaria ninguna acción |
| Número | 1 | 0.99999999 | =Round( {Column},0) |
| Moneda | $10.50 | 10.5 | =Moneda( {Column}, "#,## 0.00 ") |
| Gestión de Cuentas | 34, 343.00 | 34343 | =NumberFormat({Column},"#,##0.00") |
| **Fecha: Devuelve la hora de la época** | **1-Jan-24** | **1704047400 (época)** | =DateFormat({Column }, "d-MMM-aaaa") |
| **Tiempo: (Época del 1/1/1970 + tiempo en la celda)** | **12:30 p. m.** | **45000 (época del 1/1/1970:12:30 )** | =DateFormat({Column }-25569)\*86400, "M/d/yy")}, "hh:mm") Excel almacena las fechas como números de serie secuenciales, empezando por el 1 que representa el 1 de enero de 1900. Unix epoch, empieza el 1 de enero de 1970, 00:00:00 UTC. Para convertir de una fecha Excel a segundos de época Unix ( DateFormat requiere esto) Calcule el número de días entre la fecha Excel y la fecha de inicio de época Unix (25569) Convierta el número de días en segundos (\*86400) |
| Porcentaje | 10 % | 0.1 | =NumberFormat({Column }, "#.00%") |
| Fracción | 1/2 | 0.5 | Hacer la columna de texto en Excel |
| Ciencia | 9.88E+11 | 9.87654E+11 | Hacer que el texto de la columna en Excel (esto es si realmente desea que la notación científica para que aparezca en Apptio ) |
| Texto | Las nubes van a la deriva, los susurros resuenan, el tiempo. | Las nubes van a la deriva, los susurros resuenan, el tiempo. | No es necesaria ninguna acción |
| Especial | (91987) 654-3456 | 9.19877E+11 | Haga el texto de la columna en Excel, o escriba una fórmula para añadir texto donde sea necesario IE ="("&Left( Column,5 )&")"&Mid( Column,5,3 )&"-"&Right( Column,4 ) |
| Personalizada | 43333.45 | 43333.44555 | Haga el texto de la columna en Excel, o escriba una fórmula para formatear como desee |
| Fórmula | 100 | 100 | No es necesaria ninguna acción - Muestra los resultados de la fórmula |

Cómo se comportarán la hora y la fecha con el cambio de formato

1. Fecha - Si el valor de la fecha que entra en Apptio es un tipo de fecha de Excel, tendrá que ser convertido a Unix epoch.

   Excel almacena las fechas como números de serie secuenciales, empezando por 1 que representa el 1 de enero de 1900.   
   Época Unix, comienza el 1 de enero de 1970, 00:00:00 UTC.   
   Para convertir de una fecha Excel a segundos de época Unix ( DateFormat lo requiere)   
   Calcule el número de días entre la fecha Excel y la fecha de inicio de época Unix (25569)   
   Convierta el número de días en segundos (\*86400)

   `=DateFormat(({Column}-25569)*86400,"M/d/yy")`

**Tema principal:** [Componente de carga de tablas](../../../studio/reports/table-report-upload-component.html "Se aplica a: TBM Studio 12.9.3 y posteriores")
