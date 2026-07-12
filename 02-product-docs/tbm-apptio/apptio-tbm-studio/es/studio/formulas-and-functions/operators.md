---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Operadores"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/operators.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Operadores

**Se aplica a** : TBM Studio 12.0 y posteriores

La sintaxis de la aplicación admite muchos operadores estándar, así como operadores de rollup, que hacen referencia a las unidades de origen o destino de un rollup de datos.

Puede utilizar los siguientes operadores en fórmulas y funciones:

- **+** - Suma y [concatenación de cadenas](string-concatenation.html "Se aplica a: TBM Studio 12.0 y posteriores")
- **-** - Resta
- **\*** - Multiplicación
- **/** - División
- **=** - Igual (este operador puede utilizarse tanto con fechas y cadenas como con valores numéricos)
- **!=** - No igual
- **<** - Menos de
- **<=** - Inferior o igual a
- **>** - Mayor que
- **>=** - Mayor o igual que
- **&** - Concatenación
- **@** - Operador de rollup, fuente
- **~** - Operador de enrollado, objetivo

## Operadores de rollup

Los operadores de rollup pueden utilizarse en conjuntos de datos, pero no en tablas de informes.

A continuación se describen los operadores de rollup:

- **@SOURCE** - Se puede utilizar @ o SOURCE para representar la suma de los valores del objeto fuente que se enrollarán en la fila actual de la tabla destino.
- **~TARGET** - Se puede utilizar ~ o TARGET para representar la suma de los valores del objeto de destino que recibirán valores de la tabla de origen.

Los operadores de rollup son aplicables en dos situaciones:

- En un modelo, al pasar valores de un objeto a otro. En este caso @ o SOURCE se refiere a todas las filas que se están enrollando desde el objeto fuente, y ~ o TARGET se refiere a todas las filas a las que se están enrollando.
- En una transformación de tabla con una agrupación, puede utilizar funciones estadísticas como [PROMEDIO](functions/average.html "Devuelve el valor medio de una columna o métrica especificada."), [GRANDE](functions/large.html "Devuelve el mayor valor de una columna especificada.") y [PEQUEÑO](functions/small.html "Devuelve el valor más pequeño de una columna especificada."). Por ejemplo, puede utilizar AVERAGE(@columna) para que una celda contenga la media de la columna indicada para todas las filas de origen agrupadas. Para obtener más información, consulte [Referencia a columnas agrupadas](referencing-column-names.html "Se aplica a: TBM Studio 12.0 y posteriores"). La columna sobre la que se opera debe tener activada la opción **Agrupar por** en el panel **Detalles de columna**. Los operadores de rollup son opcionales para estas funciones.

Por ejemplo, considere la siguiente tabla de unidades para un objeto de destino llamado Servidores y una tabla de origen llamada Utilidad:

## Tabla de servidores

| Nombre de host | Centro de datos | Espacio | CPU | contar |
| --- | --- | --- | --- | --- |
| Host1 | Boston | 4 | 4 | 1 |
| Host2 | Seattle | 1 | 1 | 1 |
| Host3 | Boston | 2 | 4 | 1 |
| Host4 | Seattle | 1 | 1 | 1 |

## Mesa auxiliar

| Nº Propuesta | Nombre del servidor | contar | Coste |
| --- | --- | --- | --- |
| A | Host1 | 1 | 100 dólares |
| B | Host2 | 1 | 100 dólares |
| C | Host3 | 1 | 100 dólares |
| D | Host4 | 1 | 100 dólares |

En el caso de una acumulación directa de Utilidades a Servidores, puede asignar costos de **Todas las Utilidades** a **Servidores por Servers.Hostname** utilizando la siguiente fórmula en la opción de Asignación **avanzada** :

`=@Cost`

Es decir, para cada fila de la tabla de destino, busque las filas de la tabla de origen que coincidan con el identificador Nombre de host y asigne la suma de la columna Coste a esas filas.

La tabla de unidades resultante para Servidores es:

| Nombre de host | Centro de datos | Espacio | CPU | contar | Coste |
| --- | --- | --- | --- | --- | --- |
| Host1 | Boston | 4 | 4 | 1 | 200 dólares |
| Host2 | Seattle | 1 | 1 | 1 | 100 dólares |
| Host3 | Boston | 2 | 4 | 1 | 100 dólares |
| Host4 | Seattle | 1 | 1 | 1 | $0 |

Examinando la primera fila de la tabla de unidades anterior, el valor de la columna Coste es de 200 $ porque dos filas de la tabla de Utilidades de origen coinciden con el identificador Host1, cada una con un valor de 100 $, por lo que la suma es de 200 $. La última fila contiene 0 en la columna Coste, porque ninguna fila de la tabla de origen coincide con el identificador Hostname.Host4.

Para ilustrar el operador ~, considere la siguiente tabla de origen denominada Centros de datos:

| Centro de datos | contar | Coste |
| --- | --- | --- |
| Boston | 1 | 1000 dólares |
| Seattle | 1 | 1000 dólares |

En el caso de un rollup directo de Centros de Datos a Servidores, puede imputar costes de **Todos los Centros de Datos** a **Centro de Datos Centers.Data** utilizando la siguiente fórmula en la opción de Imputación **Avanzada** :

`=@Cost*(Servers.Space/~Servers.Space)`

Esta fórmula multiplica los valores sumados por el ratio de Espacio, que es el Espacio dividido por el Espacio total consumido por los hosts en un centro de datos determinado. En el ejemplo anterior, Boston está rodando hasta dos servidores, Host1 y Host3, por lo que para Host1 en la tabla de destino, la fórmula dice que hay que tomar el valor de Coste para el Centro de Datos de Boston ($1000) y multiplicarlo por el ratio de espacio para Host1. El ratio de espacio para Host1 se obtiene tomando el valor de la columna Espacio (4) y dividiéndolo por la suma de la columna Espacio para las filas en las que Data Center = Boston, que es 6 (4 para Host1 más 2 para Host3 ).

Así, la asignación para Host1 es:

```
=$1000 * (4 / 6)
=$1000 * 0.6667
=$666.6667
```

La tabla de unidades resultante para Servidores es:

| Nombre de host | Centro de datos | Espacio | CPU | contar | Coste |
| --- | --- | --- | --- | --- | --- |
| Host1 | Boston | 4 | 4 | 1 | 667 dólares |
| Host2 | Seattle | 1 | 1 | 1 | 500 dólares |
| Host3 | Boston | 2 | 4 | 1 | 333 dólares |
| Host4 | Seattle | 1 | 1 | 1 | 500 dólares |
