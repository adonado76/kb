---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "CopyTable función"
breadcrumb: []
source_path: "studio/apptioscript/copytable_function.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# CopyTable función

Utilice la función CopyTable para copiar tablas editables (tablas editables de informes o conjuntos de datos sin procesar) dentro de un proyecto, o a un proyecto diferente dentro de la misma instancia. Esta posibilidad de copiar tablas de transformación en distintos proyectos puede ser muy útil en una solución multiproyecto, ya que evita tener que recurrir a soluciones alternativas como exportar y volver a cargar.

## Sintaxis

```
CopyTable(path, project, tableName, timePeriod)
```

Nota: autoCheckIn es un parámetro opcional, cuyo valor por defecto es "false"

## vía de acceso

La ruta completa a la tabla de origen a copiar. La tabla de origen puede ser una tabla de informes o un conjunto de datos sin procesar.

Consejo: La fecha de la ruta no puede incluir .DateGoesHere

## Tabla de informes

Una tabla de informes es cualquier tabla que pueda visualizarse en Apptio (básicamente, cualquier cosa que tenga una ruta de datos). Para utilizarla como tabla de origen en CopyTable, sólo necesita el datapath completo. Estas rutas se utilizan para extraer información parcial o condicional de una tabla.

Para obtener la ruta de datos completa:

1. Haga clic con el botón derecho en la tabla y seleccione Mostrar ruta de datos completa.
2. Copiar y pegar en un editor de texto.
3. Elimine los saltos de línea para que la ruta sea contigua.

Ejemplo:

```
Customer.com:Project A/Data/.DateGoesHere/Example Data/.RawTable/!LIMIT[0,20]/!LIMIT_COLUMNS[]/
```

La parte “.DateGoesHere” de la ruta del informe no funcionará con CopyTable,, por lo que tendrá que editarla.

- Si está copiando de un proyecto no habilitado para tiempo, sustituya .DateGoesHere por Eon:FY2000

  Ejemplo - No temporizado:

  ```
  Customer.com:Project A/Data/Eon:FY2000/Example Data/.RawTable/!LIMIT[0,20]/!LIMIT_COLUMNS[]/
  ```
- Si está copiando desde un proyecto habilitado para tiempo, y desea copiar desde un único periodo de tiempo estático, sustituya .DateGoesHere por Mes:Año (por ejemplo, January:FY2011 )

  Ejemplo - Hora codificada:

  ```
  Customer.com:Project A/Data/January:2011/Example Data/.RawTable/!LIMIT[0,20]/!LIMIT_COLUMNS[]/
  ```
- Si está copiando desde un proyecto habilitado para el tiempo, y desea copiar desde el periodo de tiempo seleccionado en la parte superior de la página en Apptio, entonces sustituya .DateGoesHere por /<%=CurrentDate("MMMM:yyyy" )%>/

  Ejemplo - Hora codificada

  ```
  Customer.com:Project A/Data/<%=CurrentDate("MMMM:yyyy")%>/Example Data/.RawTable/!LIMIT[0,20]/!LIMIT_COLUMNS[]/
  ```

## Conjunto de datos brutos

Un conjunto de datos brutos se considera datos cargados y sin transformar que no están en una tabla de informes. La forma más sencilla de obtener la ruta de un conjunto de datos sin procesar es hacer clic en el icono URL del panel de vista previa de la tabla en la pestaña Datos.

## proyecto

El proyecto de destino debe indicarse en el formato "Nombre de dominio: Nombre del proyecto".

El dominio y el proyecto del proyecto al que se va a copiar, en la forma dominio:proyecto

Ejemplo:

`customer.com:Project B`

Consejo: Las tablas pueden copiarse dentro de un mismo proyecto. En este caso, basta con introducir el mismo proyecto en el parámetro editableTableName.

Recuerde que si copia entre dos proyectos, éstos deben residir en la misma instancia. Tenga mucho cuidado al escribir el dominio y el proyecto. Si teclea mal (y, por tanto, el dominio o el proyecto no coinciden con los existentes), se crearán otros nuevos.

## tableName

El nombre de la tabla a copiar en el proyecto

tableName es el conjunto de datos en el que está copiando su tabla editable. El formato debe indicarse simplemente como nombre del conjunto de datos.

Si su intención es copiar en un conjunto de datos existente, introduzca simplemente el nombre de ese conjunto de datos (distingue entre mayúsculas y minúsculas).

Ejemplo:

`Example Data Set`

Si desea copiar en un nuevo conjunto de datos, introduzca el nombre de un conjunto de datos que aún no exista, y se creará al ejecutar CopyTable.

Sugerencia: Si su intención es copiar en un conjunto de datos existente, y lo teclea mal, creará inadvertidamente un nuevo conjunto de datos y copiará en él, en lugar del existente previsto.

## timePeriod

El periodo de tiempo al que copiar los datos en el proyecto, en forma de mes:año.

## Directrices

Al copiar entre proyectos, los dos proyectos deben residir en la misma instancia ( URL ). Suponiendo que estén en el mismo URL, las tablas editables pueden copiarse entre proyectos o entre dominios.

| Proyectos | Directrices |
| --- | --- |
| Misma instancia, mismo dominio | El proyecto A y el proyecto B están en el mismo URL ( customer.apptio.com ), y en el mismo dominio ( customer.com ). Esto puede lograrse con CopyTable. |
| Misma instancia, diferentes dominios | El proyecto A y el proyecto B están en el mismo URL ( customer.apptio.com ), pero en dos dominios diferentes ( customer.com y test.com ). Esto puede lograrse con CopyTable. |
| Instancia diferente | El proyecto A y el proyecto B se encuentran en dos sitios web diferentes: URL ( customer-dev.apptio.com y customer-stg.apptio.com ). Tienen el mismo dominio ( customer.com ). Esto no puede lograrse con CopyTable. |

Es posible enviar mensajes push a varios destinos simultáneamente desde un único botón de origen. Para ello, configure el botón con múltiples apariciones de CopyTable( ), separadas por;.

En varias partes de la sintaxis de CopyTable, es posible que tenga que introducir un formato de Período de tiempo (por ejemplo, al designar el período de tiempo de destino).

El formato del período de tiempo debe ser siempre el siguiente: Mes:Año

Ejemplo:

`January:FY2011`

Tenga en cuenta que tiene que ser la palabra completa del mes, no una abreviatura (es decir, "enero" frente a "ene" o "01").

Utilizando la sintaxis de formato de fecha en Apptio, esto puede expresarse como "MMMM:FYyyyy"

Sugerencia:

¡Los siguientes caracteres, utilizados a menudo en el!¡FILTRO y!Las funciones NEWCOLUMN, requieren escape o codificación URL :

"

/

+

?

## Configuración de botones

Para iniciar CopyTable, puede poner la sintaxis anterior dentro de un botón en la superficie de informes.

Para configurar un botón CopyTable:

1. Cambiar al modo Edición.
2. Haga clic con el botón derecho del ratón en el botón y seleccione Propiedades.
3. Seleccione la pestaña Acciones.
4. En el campo Acción del servidor, introduzca la sintaxis CopyTable.
5. Pulse Aceptar.

Al pulsarlo, el botón iniciará CopyTable según los parámetros definidos en su sintaxis.

## Ejemplo

```
CopyTable( "demo.apptio.com:BankDemo/Reports/October:FY2010/CostModels/Default/Business Units/.Summary/!SORT[{Chargeback}|desc]/!LIMIT[0,20,add_other|0,20,add_other]/!LIMIT_COLUMNS[]/", "apptio.com:DevBlank", "MyTable", "January:FY2000")
```
