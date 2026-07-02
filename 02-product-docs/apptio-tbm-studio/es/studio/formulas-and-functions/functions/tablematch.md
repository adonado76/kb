---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "TableMatch función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/tablematch.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# TableMatch función

Devuelve un valor basado en una tabla de reglas que funciona como un conjunto de sentencias IF. Cada fila de la tabla de reglas define una regla. Las condiciones en la misma fila se combinan con AND, y los valores dentro de la misma celda se tratan como condiciones OR.

La función TableMatch sustituye a las largas y complejas sentencias IF. Utiliza una tabla de reglas para capturar la información contenida en las sentencias IF. En la tabla, cada columna representa una sentencia AND. Las entradas dentro de una columna separadas por una coma representan una sentencia OR. La última columna de la tabla representa el valor que devolverá la función. Si ninguna fila se evalúa como verdadera, se devuelve como resultado el valor de la última fila de la tabla.

## Clasificar

Desde 12.10.1, la función Tablematch() se ha mejorado para trabajar mejor con Tablas editables. Anteriormente, las Tablas editables utilizadas en Tablematch no estaban ordenadas, lo que podía provocar que se devolviera un valor incorrecto. La función TableMatch tiene 2 nuevos parámetros: sort=ColumnName y sortOrder (por defecto ascendente; utilice sortOrder=desc para descendente) para permitir a los administradores establecer la ordenación deseada para devolver los valores correctos.

- sort=ColumnName
- sortOrder

ascendente por defecto si no hay ningún parámetro

sortOrder=desc para descender

Ejemplo:

Ascendente: Resultado Coincidente =TableMatch(Rules\_Tablename, Valor, sort=ColumnName\_to\_Sort )

Descendente: Resultado Coincidente =TableMatch(Rules\_Tablename, Valor, sort=ColumnName\_to\_Sort, sortOrder=desc )

- **excluir** parámetro opcional de la función tablematch().

Ejemplo:

`=TABLEMATCH(RulesData,Value,exclude=Foo,exclude={Bar},exclude=Baz)`

A partir de la versión 12.5 +, la función de columna de ordenación TableMatch( ) también incluye un parámetro opcional "exclude" a la función tablematch(). Véase la sintaxis a modo de ejemplo.

Nota: Esta función puede tener un impacto significativo en el rendimiento. Sólo debe utilizarse en conjuntos de datos, nunca en un informe.

He aquí un ejemplo de tabla de reglas:

| A | B | C |
| --- | --- | --- |
| Seattle | Windows, UNIX | servidor |
| Seattle | ordenador portátil | Dispositivos móviles |
| Seattle | PC | escritorio |
| Estación de trabajo | Supervisar | LCD |
| Estación de trabajo | desarrollador | doble núcleo |
|  |  | desconocido |

Algunas de las normas representadas por la tabla anterior son:

- Primera fila: Si Seattle y Windows o UNIX, entonces servidor.
- Cuarta fila: Si es estación de trabajo y monitor, entonces LCD.
- Última fila: Si ninguna de las reglas se evalúa como verdadera, devuelve el valor "desconocido"

La función admite tanto texto como números.

Vea este vídeo de los Servicios Educativos de Apptio : [La función « TableMatch](https://community.ibm.com/community/user/viewdocument/the-tablematch-function-7-min?CommunityKey=44bcb0d2-5ce6-4504-89eb-019253d3b5d8&tab=librarydocuments "(se abre en una pestaña o una ventana nueva)") ».

## Valores de la tabla de reglas admitidos

¡Puede anteponer al texto el prefijo! para buscar entradas que no contengan el texto. Para los números, puede utilizar los operadores estándar: =,<, <=, >, >=,!=. Para buscar una celda vacía, introduzca la palabra **EN BLANCO** en el cuadro de filtro. ¡Para buscar celdas que no estén vacías, introduzca!**EN BLANCO** en el cuadro de filtro. Se admite el comodín \*. Las opciones de búsqueda se resumen en la siguiente tabla.

| Opción | Descripción |
| --- | --- |
| Texto | Busca "texto" Las comas pueden escaparse utilizando la barra invertida. Por ejemplo, "ABC\, Inc" marcharía "ABC, Inc". |
| text1,text2,text...n | Buscar entradas que contengan una de dos o más cadenas de texto. Se trata de una operación "o". NO coloque los valores entre paréntesis. |
| texto | Buscar entradas que no contengan "texto" |
| !(text1,text2,text...n) | Buscar entradas que no contengan dos o más cadenas de texto. Se trata de una operación AND. Una entrada sólo coincidirá si no contiene todas las cadenas de texto. |
| BLANK | Introduzca esta palabra para buscar celdas vacías. |
| !BLANK | Introduzca esta palabra para buscar celdas que no estén vacías. |
| =  >  <  >=  <=  != | Utilice estos operadores con columnas numéricas.  La coma puede utilizarse como operador "o". Por ejemplo: =10,=20 puede leerse como "igual a 10 o igual a 20"  Una coma puede utilizarse como operador "y" cuando se encierra entre paréntesis. Por ejemplo: (>10,<20) puede leerse como "mayor que 10 y menor que 20" |
| \*texto  texto\*  texto\*texto  \*texto\* | El \* indica cualquier número de caracteres que aparecen antes, después o en medio de una cadena de texto. |

## Sintaxis

TableMatch(Rules Tabla,Columna, sort=ColumnName\_to\_Sort, sortOrder=asc|desc, exclude=ColumnName\_to\_Exclude,exclude=...)

- la clasificación es opcional
- sortOrder es opcional, por defecto ascendente
- excluir es opcional

Para versiones anteriores a 12.5:

```
TableMatch(Rules Table, Column[,
          suppressNullReturnsOnMatch=true])
```

Para la versión 12.5 +:

```
TableMatch(Rules Table, Column[, specifiedColumn=column_name, useRegex=false,
          suppressNullReturnsOnMatch=true])
```

=TABLEMATCH( RulesData,Value,exclude=Foo,exclude={Bar },exclude=Baz)

## Argumentos

*Tabla de reglas*

El nombre de la tabla que contiene las reglas.

*Columna*

La columna de la tabla de reglas que contiene el valor que devolverá la función.

**AVISO**

No utilice llaves alrededor del nombre de la columna.

**Por ejemplo** :

Correcto: =Tablematch(Tabla de reglas,Servidor-Unix)

Incorrecto: =Tablematch(Tabla de reglas, {Server-Unix} )

*suppressNullReturnsOnMatch*

Si se incluye este parámetro, la función no devolverá valores nulos.

*useRegex* (Compatible con TBM Studio 12.5 +; [Más información](https://community.ibm.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=a6c0a783-3c7e-435c-bdea-824da6988f07&forceDialog=0 "(se abre en una pestaña o una ventana nueva)") )

Si se incluye este parámetro, la función utilizará expresiones regulares en la búsqueda. La tabla de coincidencias se trata como expresiones regulares.

Para obtener más información sobre la sintaxis de las expresiones regulares o para probar tus propias expresiones regulares, visita [http://www.rexegg.com/regex-quickstart.html](http://www.rexegg.com/regex-quickstart.html "(se abre en una pestaña o una ventana nueva)") y [regex101.com](http://regex101.com/ "(se abre en una pestaña o una ventana nueva)").

*specifiedColumn* (Compatible con TBM
Studio 12.5 +; [Más información](https://community.ibm.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=a6c0a783-3c7e-435c-bdea-824da6988f07&forceDialog=0 "(se abre en una pestaña o una ventana nueva)") )

Si se incluye este parámetro, la función devuelve el valor de la columna de la tabla de origen especificada si no coincide ninguna regla.

## Tipo de retorno

Serie

**Notas** :

Esta función no es compatible con la barra de fórmulas **de la cinta de opciones** ni con la función de vista previa de datos de la pestaña **Datos**.

## Ejemplos

=TableMatch(Cost Center Rules,Cost Center, sort=Cost Center, sortOrder=asc, exclude=SomeColumn1, exclude=SomeColumn2 )

Suponga que tiene datos del libro mayor como los siguientes en una tabla llamada Centro de costes:

| Nº de cuenta | Código | Coste | Fecha |
| --- | --- | --- | --- |
| 100 | RSF | 1.000 | 3 de junio de 2010 |
| 200 | RRT | 2.000 | 8 de junio de 2010 |
| 300 | CAC | 1.500 | 8 de junio de 2010 |
| 400 | CAC | 3500 | 12/6/2010 |
| 500 | SIS | 6000 | 18/6/2010 |
| 600 | SIS | 5.000 | 21/6/2010 |
| 900 | ACD | 4.500 | 21/6/2010 |

Desea asignar los costes a los siguientes objetos de centro de coste en su modelo de costes:

- Software
- Red
- Servidores
- Soporte
- Centro de datos

Para ello, debe crear una nueva columna en la tabla del libro mayor que se muestra más arriba, denominada **Centro de coste**. Para rellenar la nueva columna, se crea un nuevo conjunto de datos llamado Reglas del Centro de Coste que servirá como tabla de reglas. La tabla de reglas se muestra a continuación:

| Nº de cuenta | Código | Centro de costes |
| --- | --- | --- |
| 100 | RSF, RSG | Software |
| 200 | RRT | Red |
| 300 | CAC, CAD | Servidores |
| 400 | CAC, CAD | Soporte |
| 500 600 | SIS | Centros de datos |
|  |  | Desconocido |

Tenga en cuenta lo siguiente sobre la tabla de reglas:

- Las columnas **Acct No** y **Code** se utilizan para crear una sentencia AND. Por ejemplo, la primera fila se leería como: Si el número de cuenta es igual a 100 y el código es igual a RSF o RSG, el centro de costes es Software.
- La última fila proporciona el valor por defecto "Desconocido" si ninguna de las reglas se evalúa como verdadera.

Se introduce la siguiente función TableMatch como valor para la nueva columna:

```
=TableMatch(Cost Center Rules,Cost
      Center)
```

En la función, Cost Center Rules es el nombre de la tabla de reglas y Cost Center es el nombre de la columna que contiene los resultados.

Después de aplicar la función TableMatch, la tabla del libro mayor tiene el siguiente aspecto:

| Nº de cuenta | Código | Coste | Fecha | Centro de costes |
| --- | --- | --- | --- | --- |
| 100 | RSF | 1.000 | 3 de junio de 2010 | Software |
| 200 | RRT | 2.000 | 8 de junio de 2010 | Red |
| 300 | CAC | 1.500 | 8 de junio de 2010 | Servidores |
| 400 | CAD | 3500 | 12/6/2010 | Soporte |
| 500 | SIS | 6000 | 18/6/2010 | Centros de datos |
| 600 | SIS | 5.000 | 21/6/2010 | Centros de datos |
| 900 | ACD | 4.500 | 21/6/2010 | Desconocido |
