---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "CopyTable función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/copytable.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# CopyTable función

**Se aplica a** : TBM Studio v12.0+

## Acerca de esta tarea

La función CopyTable permite copiar tablas de informes o conjuntos de datos sin procesar. CopyTable le permite copiar tablas dentro de un proyecto, o a un proyecto diferente dentro de la misma instancia. Esta posibilidad de copiar tablas en distintos proyectos puede ser muy útil en una solución multiproyecto y evitar así la necesidad de utilizar soluciones alternativas, como exportar y volver a cargar. Además, la función CopyTable es flexible y permite copiar a un periodo de tiempo específico en un proyecto de destino.

La función CopyTable se activa mediante un botón de un informe. En el cuadro de diálogo Propiedades, active CopyTable con sintaxis en el campo Acción del servidor de la pestaña Acciones.

![](../../../resources/images/studio_images/studioimages/studio/stu277.png)

## Panorama general y limitaciones

Antes de utilizar CopyTable, revise y comprenda los siguientes conceptos importantes sobre las capacidades de esta función:

- La ruta de la tabla CopyTable debe estar codificada en URL. Para obtener la ruta de la tabla, haga clic con el botón derecho en la tabla y seleccione **Mostrar ruta de datos completa**. Si la ruta no está codificada, debe escapar los siguientes caracteres especiales URL : " / +?

  Busca en Internet información sobre cómo escapar de los personajes.
- La tabla de destino es siempre un conjunto de datos, a diferencia de la fuente, que puede ser una tabla de informes o un conjunto de datos sin procesar. Los conjuntos de datos existentes en el destino pueden sobrescribirse, o pueden crearse nuevos conjuntos de datos.
- Al copiar entre proyectos, los dos proyectos deben residir en la misma instancia ( URL ). Suponiendo que los proyectos estén en el mismo URL, las tablas pueden copiarse entre proyectos o entre dominios.

  Ejemplos
  :   **Ejemplo 1** : (Misma instancia, mismo dominio): El proyecto A y el proyecto B están en la misma URL ( customer.apptio.com ), y el mismo dominio ( customer.com ). CopyTable se **puede** utilizar.

      **Ejemplo 2** : (Misma instancia, dominios diferentes): El proyecto A y el proyecto B están en el mismo URL ( customer.apptio.com ), pero en dos dominios diferentes ( customer.com y test.com ). CopyTable **no se puede** utilizar.

      **Ejemplo 3** : (Instancia diferente): El Proyecto A y el Proyecto B se encuentran en dos URL diferentes ( customer-dev.apptio.com y customer-stg.apptio.com ). Tienen el mismo dominio ( customer.com ). CopyTable **no se puede** utilizar.
- Puede copiar en varios destinos simultáneamente desde un único botón de origen. Para ello, configure el botón con múltiples apariciones de CopyTable( ), separadas por una nueva línea.
- El formato del período de tiempo utilizado en CopyTable debe ser siempre Mes:Año fiscal o Período:Año fiscal (ejemplo: January:FY2011 o P1:FY2011 ). Para los calendarios gregorianos, puede utilizar la palabra completa del mes o la abreviatura de tres letras (por ejemplo: enero o ene). Utilizando la sintaxis de formato de fecha de la aplicación, se puede expresar como MMMM:ffff. Para los tipos de calendario de periodos, puede utilizar ppp:ffff.

## Dónde utilizarlo

Utilice la sintaxis en el campo **Acción del servidor** de un botón de un informe.

## Sintaxis

```
CopyTable("Source Table","Destination Project","Destination Data Set","Time Period
        to Copy To", autocheckin=”true”|”false”)
```

Nota: Cada argumento debe ir entre comillas.

## Argumentos

**Tabla** de origen - La tabla de origen puede ser una tabla de informe o un conjunto de datos sin procesar.

**Tabla** de informes - Una tabla de informes es cualquier tabla que se pueda ver en la aplicación (básicamente cualquier cosa que tenga una ruta de datos). Para utilizarla como tabla de origen en CopyTable, sólo necesita la ruta de datos completa. Para obtener la ruta de datos completa:

1. Haga clic con el botón derecho en la tabla y seleccione Mostrar ruta de datos completa. Consulte la sección Cómo: Utilizar la ruta de datos completa para obtener más información.
2. Copie y pegue la ruta de los datos en un editor de texto.
3. Elimine los saltos de línea para que la ruta de datos esté en una sola línea.
4. Sustituya la cadena .DateGoesHere por un período de tiempo adecuado. Consulte Período de tiempo en el que copiar para obtener más información sobre cadenas de período de tiempo válidas.
5. Elimina la cadena add\_total si está presente para evitar tener una fila de totales en el destino.

Por ejemplo, supongamos que empiezas con la siguiente ruta de datos (fíjate en las partes en rojo):

```
customer.com:Test Project A/
Reports/
.DateGoesHere/
CostModels/
Default/
Test/
!GROUPBY[{Test Table.Item},{Test Table.Group}]/
.Summary/
!SORT[{Cost}|desc]/
!FILTER_ZERO[{Cost}]/
!PIVOT2[{Test Table.Item}][{Test Table.Group}][{Cost}]/
!LIMIT[0,2147483647,add_total]/
!LIMIT_COLUMNS[][][][orderByIncludeList] /
```

Se editaría de la siguiente manera si se quisiera utilizar un periodo de tiempo dinámico como fuente.

```
customer.com:Test Project A/Reports/<%=CurrentDate("ppp:ffff")%>/CostModels/Default/Test/!GROUPBY[{Test Table.Item},{Test Table.Group}]/.Summary/!SORT[{Cost}|desc]/!FILTER_ZERO[{Cost}]/!PIVOT2[{Test Table.Item}][{Test Table.Group}][{Cost}]/!LIMIT[0,2147483647]/!LIMIT_COLUMNS[][][][orderByIncludeList]/
```

## **Conjunto de datos brutos**

Se considera un conjunto de datos brutos cualquier dato cargado y sin transformar que no esté en una tabla de informe.

Para obtener la ruta a un conjunto de datos sin procesar de /data, siga estos pasos:

1. Navegue hasta la tabla en TBM Studio.
2. Seleccione **Tabla** en el canal Pasos.
3. Copie el segmento del URL después del -@C. **Ejemplo** : Parte relevante de URL resaltada:![](https://help.apptio.com/en-us/resources/images/studio_images/studioimages/studio_acme%20gl_table.png)
4. Sustituya %253A por %3A y .DateGoesHere por una cadena horaria adecuada.
5. Copie el segmento del URL después del -@C. **Ejemplo** : Parte relevante de URL resaltada:![](https://help.apptio.com/en-us/resources/images/studio_images/studioimages/studio_acme%20gl_table.png)
6. Sustituya %253A por %3A y .DateGoesHere por una cadena horaria adecuada.

Consulte la siguiente sección, Tiempo para la fuente, para obtener más información sobre lo que puede sustituir a .DateGoesHere.

- **Original** - reference.apptio.com%253ACost+Transparency/Data/.DateGoesHere/Acme+GL
- **Sustitución** - reference.apptio.com%3ACost+Transparency/Data/Jan:FY2018/Acme+GL

## Hora de la fuente

Cuando elabore la fuente para una operación CopyTable( ), debe especificar un periodo de tiempo válido. Este periodo de tiempo se inyecta en .DateGoesHere al examinar las trayectorias mostradas en la sección anterior. **No** es la fecha actual del calendario. Dependiendo de la situación, puede que necesite utilizar un periodo de tiempo específico (por ejemplo: Jan:FY2018, September:2018, etc.), o puede que desee algo dinámico que se ejecute dentro del periodo de tiempo que tenga seleccionado actualmente en el selector de fechas. Puede especificar periodos de tiempo como:

## Proyecto no temporal

Si está copiando de un proyecto que **no** está habilitado para el tiempo, entonces sólo hay un período de tiempo elegible para obtener la ruta de Eon:FY2000. Aquí tienes un ejemplo de lo que harías en ese caso:

- **Original** - customer.com%3AProject+A/Data/.DateGoesHere/Example+Data+Set/
- **Sustitución** - customer.com%3AProject+A/Data/Eon:FY2000/Example+Data+Set/

## Proyecto temporal

Si está copiando desde un proyecto con tiempo activado, tiene dos opciones:

1. Sustituya .DateGoesHere por una cadena de fecha válida, como se muestra aquí:
   - **Original** - customer.com%3AProject+A/Data/.DateGoesHere/Example+Data+Set/
   - **Sustitución** - customer.com%3AProject+A/Data/January:FY2011/Example+Data+Set/
2. Reemplace el .DateGoesHere con [wikitext](https://community.apptio.com/docs/DOC-5729 "(se abre en una pestaña o una ventana nueva)") llamando a la [función CurrentDate](https://help.apptio.com/en-us/studio/formulas-and-functions/functions/currentdate.htm "(se abre en una pestaña o una ventana nueva)") como se muestra aquí:
   - **Original** - customer.com%3AProject+A/Data/.DateGoesHere/Example+Data+Set/
   - **Sustitución** - customer.com%3AProject+A/Data/<%=CurrentDate( "ppp:ffff")%>/Ejemplo+Datos+Set/

## Proyecto de destino

El proyecto de destino debe indicarse en el formato Nombre del dominio:Nombre del proyecto.

**Ejemplo** : customer.com:Project B.

Nota:

**No** es necesario codificar el nombre del proyecto. Si hay espacios en el nombre, deben conservarse y **no** sustituirse por caracteres de codificación.

## Conjunto de datos de destino

El conjunto de datos de destino debe ser una tabla sin procesar. No puede ser una tabla de transformación. La tabla de destino se proporciona como una cadena entre comillas, que es simplemente el nombre de la tabla. Los espacios están permitidos y no es necesario codificarlos.

**Ejemplo** : Proyecto B

Sugerencia:

- Las tablas pueden copiarse dentro de un mismo proyecto. En este caso, basta con introducir el mismo proyecto en el parámetro Proyecto de destino.
- Si se copia entre dos proyectos, éstos deben residir en la misma instancia.

## Periodo de tiempo al que se copia

Es el periodo de tiempo de destino al que desea que se apliquen los datos.

Dependiendo del escenario temporal, puede ser necesaria una sintaxis diferente.

- Si está copiando en un proyecto no temporizado, introduzca Eon:FY2000**.NOTICE**

  R12 requiere que tenga configurado el tiempo por lo que esto sólo se aplica a R11.
- Si está copiando en un proyecto temporal y desea copiar en un periodo de tiempo específico y estático, deberá codificar un valor de Periodo:Año Fiscal (ejemplo: January:FY2011 ).
- Si está copiando desde un proyecto habilitado para tiempo, y desea conducir el período de tiempo de destino basado en el período de tiempo seleccionado en la parte superior del informe en la aplicación, entonces puede utilizar <%=CurrentDate("ppp:ffff" )%>.

En este momento, no puede copiar desde un proyecto no habilitado para tiempo y seleccionar dinámicamente un mes de destino específico.

## Controlar los permisos de edición en el destino

Si está copiando desde una tabla de origen que es editable, entonces la tabla sin procesar tendrá una columna.PK cuando se copie. Apptio reconocerá la tabla como editable. ¡Si no desea que la tabla de destino sea editable, deberá filtrar la columna.PK utilizando el parámetro!LIMIT\_COLUMN como se muestra aquí:

`customer.com%3AProject+A/Data/<%=CurrentDate("ppp:ffff")%>/Example+Data+Set/!LIMIT_COLUMNS[][][{.PK}]`

## Configurar un botón para utilizar CopyTable

Para configurar un botón de un informe para que utilice CopyTable:

1. Navegue hasta el informe en TBM Studio ( r12 ) o cambie al modo Edición ( r11 ).
2. Añade un botón y nómbralo adecuadamente.
3. Haga clic con el botón derecho del ratón en el botón y seleccione Propiedades.
4. Seleccione Acciones.
5. En el campo Acción del servidor, introduzca la sintaxis CopyTable.

Ahora, cuando un usuario haga clic en el botón, se ejecutará la función CopyTable.

Un botón puede configurarse para ejecutar varias funciones CopyTable poniendo más de una función CopyTable( ) en el campo Acción del servidor. Cada función debe separarse con un retorno de línea de nueva línea.

**Ejemplo** : Suponga que desea copiar una tabla del Proyecto A a los Proyectos B, C y D. Introduzca las siguientes funciones CopyTable en el campo **Acción del servidor** :

```
CopyTable("customer.com%3AProject+A/Data/<%=CurrentDate("ppp:ffff")%>/Example+Data+Set/","customer.com:Project
          B","Example Data Set","<%=CurrentDate("ppp:ffff")%>")
```

```
CopyTable("customer.com%3AProject+A/Data/<%=CurrentDate("ppp:ffff")%>/Example+Data+Set/","customer.com:Project
          C","Example Data Set","<%=CurrentDate("ppp:ffff")%>")
```

```
CopyTable("customer.com%3AProject+A/Data/<%=CurrentDate("ppp:ffff")%>/Example+Data+Set/","customer.com:Project
          D","Example Data
    Set","<%=CurrentDate("ppp:ffff")%>")
```

## Ejemplos

- **Ejemplo 1** - Copiar un conjunto de datos en el Proyecto A a un conjunto de datos en el Proyecto B ( R11 solamente, tiempo desactivado en ambos proyectos). Nota: el siguiente ejemplo se envuelve, pero está todo en una sola línea.

  ```
  CopyTable("customer.com%3AProject+A/Data/Eon%3A2000/Example+Data+Set/","customer.com:Project
                B","Example Data Set","Eon:2000")
  ```
- **Ejemplo 2** - Copiar un conjunto de datos en el Proyecto A a un conjunto de datos del mismo nombre en el Proyecto B (tiempos específicos). Nota: el siguiente ejemplo se envuelve, pero está todo en una sola línea.

  ```
  CopyTable("customer.com%3AProject+A/Data/Jan%3AFY2019/Example+Data+Set/",
                  "customer.com:Project B","Example Data
                Set","January:FY2018")
  ```
- **Ejemplo 3** - Copiar un conjunto de datos en el Proyecto A a un nombre diferente en el mismo proyecto (período de tiempo dinámico). Nota: el siguiente ejemplo se envuelve, pero está todo en una sola línea.

  ```
  CopyTable("customer.com%3AProject+A/Data/<%=CurrentDate("ppp:ffff")%>/Original+Data+Set/",
                "customer.com:Project A","Another Data
                Set","<%=CurrentDate("ppp:ffff")%>")
  ```
- **Ejemplo 4** - Copiar un conjunto de datos editables en el Proyecto A al Proyecto B convirtiéndolo en no editable - ( R11 only, dynamic time period). Nota: el siguiente ejemplo se envuelve, pero está todo en una sola línea.

  ```
  CopyTable("customer.com%3AProject+A/Data/<%=CurrentDate("ppp:ffff")%>/Editable+Data+Set/!LIMIT_COLUMNS[][][{.PK}]",
                  "customer.com:Project A","Data
                Set","<%=CurrentDate("ppp:ffff")%>")
  ```
- **Ejemplo 5** - Copiar una vía de acceso de informe en el Proyecto A a un conjunto de datos en el Proyecto B (período de tiempo dinámico). Nota: el siguiente ejemplo se envuelve, pero está todo en una sola línea.

  ```
  CopyTable("customer.com:Test Project
                  A/Reports/<%=CurrentDate("ppp:ffff")%>/CostModels/Default/.View:Report
                  Name/Source/!GROUPBY[{Source.UID},{Source.Group}]/.Summary/!SORT[{Cost}|desc]/!LIMIT[0,2147483647]/!LIMIT_COLUMNS[{Source.UID},{Source.Group},{Cost}][][][orderByIncludeList]/","customer.com:Test
                  Project B","Table
                Name","<%=CurrentDate("ppp:ffff")%>")
  ```
- **Ejemplo 6** - Copiar una vía de acceso de informe en el Proyecto A a un conjunto de datos en el mismo proyecto (período de tiempo dinámico). Nota: el siguiente ejemplo se envuelve, pero está todo en una sola línea.

  ```
  CopyTable("customer.com:Test Project
                A/Reports/<%=CurrentDate("ppp:ffff")%>/CostModels/Default/.View:Report
                Name/Source/!GROUPBY[{Source.UID},{Source.Group}]/.Summary/!SORT[{Cost}|desc]/!LIMIT[0,2147483647]/!LIMIT_COLUMNS[{Source.UID},{Source.Group},{Cost}][][][orderByIncludeList]/","customer.com:Test
                Project A","Table Name","<%=CurrentDate("ppp:ffff")%>")
  ```
