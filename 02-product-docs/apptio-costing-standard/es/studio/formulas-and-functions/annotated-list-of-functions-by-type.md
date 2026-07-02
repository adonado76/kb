---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Lista anotada de funciones por tipo"
breadcrumb: []
source_path: "studio/formulas-and-functions/annotated-list-of-functions-by-type.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Lista anotada de funciones por tipo

**Se aplica a** : TBM Studio 12.0 y posteriores

La siguiente información resume las funciones y su sintaxis por tipo. Las funciones se clasifican por tipos:

- Base de datos
- Fecha y hora
- Formateado
- Matemáticas
- Serie
- Transformación de la tabla

## Apptio informes relacionados con el proyecto

## Funciones de la base de datos

| **Función** | **Descripción** |
| --- | --- |
| [CopyTable](functions/copytable.html "Se aplica a: Estudio TBM v12.0+") | ``` CopyTable("Source Table","Destination Project","Destination Data Set","Time               Period to Copy To") ``` |
| [GetInfo](functions/getinfo.html "Se aplica a: TBM Studio 12.0 y posteriores") | `GETINFO("attribute1",["DomainName:ProjectName"]` |
| [Si](functions/if.html "Evalúa una expresión de filtro y devuelve un valor si es verdadero y otro si es falso. Admite operaciones AND y OR en la condición.") | `If(filter_expression,true_expression,false_expression)` |
| [Clave](functions/key-function.html "Se aplica a: TBM Studio 12.0 y posteriores") | `Key(value1,value2,...)` |
| [PeriodsInHalf](functions/periodsinhalf.html "Se aplica a: TBM Studio y posteriores") | `PeriodsInHalf(half)` |
| [PeriodsInQuarter](functions/periodsinquarter.html "Se aplica a: TBM Studio y posteriores") | `PeriodsInQuarter(quarter)` |
| [PeriodsInYear](functions/periodsinyear.html "Se aplica a: TBM Studio y posteriores") | `PeriodsInYear()` |
| [Sustituir](functions/replace.html "Sustituye los valores de una tabla basándose en las correspondencias de otra tabla de consulta. La función coincide en las columnas clave y asigna nuevos valores de las columnas especificadas en la tabla de sustitución. Todos los valores se tratan como cadenas.") | `=Replace((transform_table_column1,transform_table_column2,...),search_and_replace_table,(match_column1,match_column2,...),(new_column1,new_column2,...),replace_table_column)` |
| [Fila](functions/row.html "Devuelve el índice de la fila actual de la tabla, empezando por cero para la primera fila.") | ``` Row(               ) ``` |
| [RowCount](functions/rowcount.html "Devuelve un recuento del número total de filas de una tabla especificada. Si no se especifica ninguna tabla, devuelve el número de filas en el contexto de la tabla actual.") | `RowCount(table)` |
| [TableMatch](functions/tablematch.html "Devuelve un valor basado en una tabla de reglas que funciona como un conjunto de sentencias IF. Cada fila de la tabla de reglas define una regla. Las condiciones en la misma fila se combinan con AND, y los valores dentro de la misma celda se tratan como condiciones OR.") | `TableMatch(Table,Column)` |
| [UniqueCount](functions/uniquecount.html "Se aplica a: TBM Studio 12.0 y posteriores") | `UniqueCount(column)` |
| [UniqueValues](functions/uniquevalues.html) | `UniqueValues(column)` |

## Funciones de fecha y hora

| Función | Sintaxis |
| --- | --- |
| [CurrentDate](functions/currentdate.html "Devuelve la fecha de inicio del periodo de tiempo actualmente seleccionado, si el tiempo está activado. Si no, devuelve Eon 2000.") | `CurrentDate([format_string])` |
| [días](functions/days.html "Convierte una fecha especificada en un valor numérico que representa el número de días transcurridos desde el 1 de enero de 1970.") | `Days(date_expression)` |
| [DurationOfMonth](functions/durationofmonth.html) | `DurationOfMonth ("d/h/m/s/S", [month[, year]])` |
| [Transcurrido](functions/elapsed.html "Calcula el tiempo transcurrido entre dos fechas en segundos, teniendo en cuenta opcionalmente los periodos excluidos y ofreciendo una salida formateada.") | `Elapsed(startDate,endDate[,table[,startCol,endCol])` |
| [Horas](functions/hours.html "Convierte un valor de fecha en el número de horas transcurridas desde el 1 de enero de 1970, como valor numérico.") | `Hours(date_expression)` |
| [Minutos](functions/minutes.html "Convierte un valor de fecha en el número de minutos transcurridos desde el 1 de enero de 1970, como valor numérico.") | `Minutes(date_expression)` |
| [Meses](functions/months.html "Convierte una fecha especificada en un valor decimal que representa el número de períodos desde el 1 de enero de 1970. Útil para cálculos basados en el tiempo, como la determinación de duraciones o el prorrateo de costes.") | `Months(date_expression)` |
| [Ahora](functions/now.html) | `Now(metric)` |
| [Periodo](functions/period.html "Se aplica a: TBM Studio 12.0 y posteriores") | `Period(["time_period"][n])` |

## Funciones de formato

| Función | Sintaxis |
| --- | --- |
| [Moneda](functions/currency.html "Formatea valores numéricos como cadenas monetarias, añadiendo el símbolo monetario apropiado en función de la configuración regional. Por defecto, los valores negativos se muestran en rojo.") | `Currency(column[,pattern[;negative_pattern]])` |
| [DateFormat](functions/dateformat.html "Convierte una expresión de fecha a un formato de fecha especificado.") | `DateFormat(date_expression,format_string)` |
| [NumberFormat](functions/numberformat.html "Da formato a un valor numérico en una etiqueta (cadena) utilizando patrones personalizados para números positivos y negativos, duraciones o formato de tamaño de datos. Esta función está diseñada para su uso en columnas de tipo Etiqueta.") | `NumberFormat(column[,pattern[;negative_pattern]])` |
| [StatusIcon](functions/statusicon.html "Se aplica a: TBM Studio 12.0 y posteriores") | `StatusIcon(green_expression,red_expression)` |

## Funciones matemáticas

| Función | Sintaxis |
| --- | --- |
| [Abs](functions/abs-function.html "Devuelve el valor absoluto de un número o expresión, eliminando cualquier signo negativo.") | `Abs(column)` |
| [Anual](functions/annual.html "Devuelve un valor para la métrica especificada ajustado hacia delante o hacia atrás en un número de años, en función del tipo de calendario seleccionado.") | `Annual(metric[,delta[,type]])` |
| [Anualizar](functions/annualize.html "Se aplica a: TBM Studio 12.0 y posteriores") | `Annualize(metric)` |
| [Promedio](functions/average.html "Devuelve el valor medio de una columna o métrica especificada.") | `Average(rollup_operator column)` |
| [DateSum](functions/datesum.html "Suma los valores de todas las columnas cuyos nombres se ajustan a los formatos de fecha reconocidos, ignorando las columnas no fechadas.") | `DateSum()` |
| [Grande](functions/large.html "Devuelve el mayor valor de una columna especificada.") | ``` Large               (rollup_operator column) ``` |
| [Máx](functions/max.html "Compara dos expresiones y devuelve el valor mayor.") | `Max(numeric_expression,numeric_expression)` |
| [Mín](functions/min.html "Compara dos expresiones numéricas y devuelve el valor menor.") | `Min(numeric_expression,numeric_expression)` |
| [Mod](functions/mod.html "Divide un número por otro y devuelve el resto, conservando el signo del dividendo (primer número).") | `Mod(number,divisor)` |
| [Percentil](functions/percentile.html "Devuelve el valor del percentil especificado para una columna numérica dada. Un percentil representa el valor por debajo del cual se sitúa un determinado porcentaje de los datos.") | `Percentile(rollup_operator column,percentage)` |
| [Alimentación](functions/power.html "Eleva un número base especificado a la potencia de un exponente especificado, realizando un cálculo exponencial.") | `Power(base,exponent)` |
| [PreviousMonth](functions/previousmonth.html "Devuelve el valor de una métrica especificada del mes anterior dentro de la misma tabla. Útil para comparar los valores actuales con los del mes anterior.") | `PreviousMonth(metric)` |
| [PreviousYear](functions/previousyear.html "Devuelve la suma de una métrica especificada en la tabla actual para el número anterior de periodos de un ejercicio. En un calendario de 12 periodos, serían 12 periodos. En un calendario de 13 periodos, serían 13 periodos.") | `PreviousYear(metric)` |
| [QuarterToDate](functions/quartertodate.html "Devuelve el valor acumulado de una métrica especificada desde el comienzo del trimestre fiscal actual hasta el período actual inclusive.") | `QuarterToDate(column)` |
| [Rand](functions/rand.html "Genera un número decimal aleatorio entre 0.0 (inclusive) y 1.0 (exclusive).") | ``` Rand(               ) ``` |
| [Proporción](functions/ratio.html "Se aplica a: TBM Studio 12.0 y posteriores") | `Ratio(column,~column)` |
| [Redondear](functions/round.html "Redondea un número real a un número especificado de decimales utilizando el algoritmo 'round-half-up'. Esto significa que los valores que terminan en.5 se redondean a partir de cero.") | `Round(numeric_expression,digits)` |
| [SLN](functions/sln.html "Se aplica a: TBM Studio 12.0 y posteriores") | `SLN(original,salvage,lifespan)` |
| [Pequeña](functions/small.html "Devuelve el valor más pequeño de una columna especificada.") | `Small(rollup_operator column)` |
| [Suma](functions/sum.html "Devuelve la suma total de los valores de la columna numérica especificada.") | `Sum(column)` |
| [TimePeriod](functions/timeperiod.html "Devuelve el valor de una métrica especificada en la misma tabla para una unidad de tiempo (por ejemplo, mes, trimestre, año) que es un número especificado de unidades antes o después del período actual. Un desplazamiento de 0 devuelve el valor del periodo actual. La unidad de tiempo viene determinada por la vista seleccionada o por un sufijo de granularidad explícito.") | `TimePeriod(metric,time)` |
| [Trunc](functions/trunc.html "Trunca un número real eliminando su parte fraccionaria.") | `Trunc(value)` |
| [Desmarque](functions/untag.html "Se aplica a: TBM Studio 12.0 y posteriores") | `Untag(value)` |
| [YearToDate](functions/yeartodate.html "Devuelve el valor acumulado de una métrica especificada desde el comienzo del ejercicio en curso hasta el período actual inclusive. Esto difiere de la función Anual, que siempre devuelve el total de todo el año, independientemente del periodo actual.") | `YearToDate(column)` |

## Funciones de cadena

| Función | Sintaxis |
| --- | --- |
| [CapFirstLetter](functions/capfirstletter.html "Pone en mayúsculas la primera letra de cada palabra del argumento de cadena y en minúsculas todas las demás letras.") | `CapFirstLetter(string)` |
| [Eval](functions/eval.html "Se aplica a: TBM Studio 12.0 y posteriores") | `Eval(string)` |
| [EvalWiki](functions/evalwiki.html "Se aplica a: TBM Studio 12.0 y posteriores") | `EvalWiki(wikitext)` |
| [Buscar](functions/find.html "Devuelve la posición de la primera aparición de una cadena de búsqueda dentro de otra cadena, comenzando en una posición opcional. Esta función distingue entre mayúsculas y minúsculas.") | `Find(search_string,in_string,[starting_position])` |
| [Búsqueda de IP](functions/iplookup.html "Se aplica a: TBM Studio 12.0 y posteriores") | ``` IPLookup(source_column,lookup_table,matching_column,replacement_column               ,default_value) ``` |
| [IsNumeric](functions/isnumeric.html "Evalúa una expresión para determinar si es un número válido, devolviendo 'verdadero' o 'falso' como cadena.") | `IsNumeric("value") or ISNUMERIC({column name})` |
| [Izquierda](functions/left.html "Devuelve un número determinado de caracteres de una cadena (incluidos los espacios en blanco), empezando por la izquierda.") | `Left(string[,count])` |
| [Len](functions/len.html "Devuelve el número de caracteres de una cadena dada, incluidos los espacios.") | `Len(string_expression)` |
| [Función de búsqueda](functions/lookup.html "Busca un valor en una tabla de consulta basándose en una coincidencia entre una columna de la tabla actual y una columna de la tabla de consulta, y devuelve el valor correspondiente de una columna de sustitución.") | ``` Lookup(source_column, lookup_table, matching_column, replacement_column, leave_original_value, replace_nulls, ignore_case, default_value) ``` |
| [Función Lookup\_Wild](functions/lookup_wild.html "Busca un valor en una tabla de búsqueda utilizando la coincidencia de patrones (expresiones regulares) en la columna coincidente y devuelve el valor correspondiente de una columna de sustitución.") | ``` Lookup_Wild(source_column, lookup_table, matching_column, replacement_column, leave_original_value, replace_nulls, ignore_case, default_value) ``` |
| [LookupEx](functions/lookupexandlookupex_wild.html "Realiza una búsqueda en las tablas y devuelve todos los valores coincidentes, creando nuevas filas para cada coincidencia. Esta función permite establecer una relación de uno a muchos uniendo cada fila coincidente de la tabla de búsqueda en la tabla transformada.") | ``` LookupEx(source_column,lookup_table,matching_column,replacement_column               [,leave_original_value][,replace_nulls][,ignore_case]) ``` |
| [LookupFromPath](functions/lookupfrompath.html "Se aplica a: TBM Studio 12.0 y posteriores") | `LookupFromPath("path",target_column,lookup_column,lookup_value_column)` |
| [LookupObjectTotalAllocated](functions/lookupobjecttotalallocated.html "Se aplica a: TBM Studio 12.0 y posteriores") | `LookupObjectTotalAllocated(metric)` |
| [LookupObjectTotalValue](functions/lookupobjecttotalvalue.html "Se aplica a: TBM Studio 12.0 y posteriores") | ``` LookupObjectTotalValue(object[,metric  [, driver]]) ``` |
| [LookupObjectUnitAllocated](functions/lookupobjectunitallocated.html "Se aplica a: TBM Studio 12.0 y posteriores") | ``` LookupObjectUnitAllocated  (sourceObject,destObject,metric,  columnInLocalTable,columnInSourceObjectTable) ``` |
| [LookupObjectUnitValue](functions/lookupobjectunitvalue.html "Se aplica a: TBM Studio 12.0 y posteriores") | ``` LookupObjectUnitValue  (object,metric,targetCol,lookupCol[,driver]) ``` |
| [LookUpMetric](functions/lookupmetric.html "Se aplica a: TBM Studio 12.0 y posteriores") | `LookUpMetric(metric,column)` |
| [Inferior](functions/lower.html "Convierte la cadena de entrada a minúsculas. caracteres") | `Lower(expression)` |
| [Medio](functions/mid.html "Devuelve un número especificado de caracteres de una cadena, comenzando en una posición dada desde la izquierda.") | `Mid(string,start[,count])` |
| [Pluralizar](functions/pluralize.html "Se aplica a: TBM Studio 12.0, 12.1") | `Pluralize(noun[,count])` |
| [Derecha](functions/right.html "Devuelve el número especificado de caracteres desde el final (lado derecho) de una cadena, incluidos los espacios en blanco.") | `Right(string[,count])` |
| [Búsqueda](functions/search.html) | `Search(search_string,in_string[,starting_position])` |
| [Dividir](functions/split.html "Se aplica a: TBM Studio 12.0 y posteriores") | `Split(expression,n[,delimiters])` |
| [Sustituir](functions/substitute.html) | `Substitute(target_string,search_string,replacement_string)` |
| [Recortar](functions/trim.html "Elimina los espacios iniciales y finales de una cadena especificada. No elimina los espacios dentro de una cadena.") | `Trim(expression)` |
| [Desatornillar](functions/undrill.html "Se aplica a: TBM Studio 12.0 y posteriores") | `Undrill(metric)` |
| [Superior](functions/upper.html "Convierte la cadena de entrada a todos los caracteres en mayúsculas.") | `Upper(expression)` |
| [Valor](functions/value.html "Convierte una cadena de aspecto numérico en un número utilizando un patrón de formato opcional. Útil para extraer valores numéricos de cadenas que incluyen texto o símbolos.") | `Value(value[,pattern])` |

## Funciones de transformación de tablas

| Función | Sintaxis |
| --- | --- |
| [Usar\_Mapa\_rejilla](functions/usemapgrid.html "Se aplica a: TBM Studio 12.0 y posteriores") | `Use_Map_Grid(table:source_column[,notation])` |
| [Utilizar\_Mapa\_Tabla](functions/usemaptable.html "Se aplica a: TBM Studio 12.0 y posteriores") | ``` Deprecated.               Replaced by Use_Map_Grid. ``` |

## Apptio funciones relacionadas con el proyecto

| Función | Sintaxis |
| --- | --- |
| [DomainName](functions/domainname.html "Se aplica a: TBM Studio 12.0 y posteriores") | ``` DomainName(               ) ``` |
| [ProjectExists](functions/project-exists-function.html "Se aplica a: TBM Studio 12.0 y posteriores") | `ProjectExists(domain:project)` |
| [ProjectName](functions/projectname.html "Se aplica a: TBM Studio 12.0 y posteriores") | ``` ProjectName               ( ) ``` |

## Funciones de los informes

| Función | Sintaxis |
| --- | --- |
| [GetLastFilterColumn](functions/getlastfiltercolumn.html "Se aplica a: TBM Studio 12.0 y posteriores") | `GetLastFilterColumn()` |
| [GetLastFilterValue](functions/getlastfiltervalue.html "Se aplica a: TBM Studio 12.0 y posteriores") | `GetLastFilterValue(column)` |
| [GetReportName](functions/getreportname.html "Se aplica a: TBM Studio 12.0 y posteriores") | `GetReportName()` |
| [GetReportPath](functions/getreportpath.html "Se aplica a: TBM Studio 12.0 y posteriores") | `GetReportPath()` |
| [Icono](functions/icon.html "Se aplica a: TBM Studio 12.0 y posteriores") | `Icon(["icon-type"], expression, expression+)` |
| [ObjectName](functions/objectname.html "Se aplica a: TBM Studio 12.0 y posteriores") | `ObjectName()` |
| [Gráfico de línea](functions/sparkline.html "Se aplica a: TBM Studio 12.0 y posteriores") | `Sparkline(past,future,column)` |
