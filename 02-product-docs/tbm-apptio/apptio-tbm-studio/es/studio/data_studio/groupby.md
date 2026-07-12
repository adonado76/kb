---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "GROUPBY"
breadcrumb: []
source_path: "studio/data_studio/groupby.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# GROUPBY

¡El!La función GROUPBY agrupa las entradas de una tabla en función del valor de una columna específica. Puede agrupar varias columnas con la **cinta de opciones**.

!GROUPBY es una de las funciones de tabla más utilizadas. Toma una tabla y la resume en función de los valores de una columna determinada. Una vez agrupados, ya no verá los detalles de cada línea, aunque habrá enlaces que lleven a vistas detalladas.

Nota: Hay un límite de 15 columnas en una línea GroupBy para las configuraciones de tablas de informes.

Existen tres versiones de la función:

- !GROUPBY[nombre de columna]
- !GROUPBY[nombre columna,nombre columna]
- !GROUPBY[nombre columna|nombre columna]

## !GROUPBY[nombre de columna]

Esta es la versión más sencilla de la función. Agrupa las filas de una tabla por el nombre de columna proporcionado.

## Ejemplo

Suponga que tiene la tabla que se muestra en la figura siguiente.

![Ejemplo](../../resources/images/it%20planning_images/groupby-1.png)

A continuación se muestra la ruta de datos utilizada para generar la tabla:

```
docs.org:ABC Company/
Default/
.TableTransform:Data Center Services/
.Summary
```

Supongamos que desea agrupar la tabla por centro de datos. ¡Añade el!GROUPBY a la ruta de datos como se muestra a continuación.

```
docs.org:ABC Company/
Reports/
.DateGoesHere/
CostModels/
Default/
.TableTransform:Data Center Services/
!GROUPBY[Data Center]/
.Summary
```

El resultado se muestra en la siguiente figura. Observe que las entradas de la columna Centro de datos son ahora enlaces que llevan a vistas detalladas de cada centro de datos. Además, Apptio añade una columna Recuento que indica el número de entradas que componen cada agrupación.

![Servicios de centro de datos](../../resources/images/it%20planning_images/groupby-2.png)

## !GROUPBY[nombre columna,nombre columna]

¡Esta versión del!La función GROUPBY agrupa filas por dos o más columnas. Los nombres de las columnas se separan por comas. El orden en que se introducen los nombres de las columnas determina el orden utilizado para agrupar las filas y el orden en que se muestran las columnas.

## Ejemplo

Supongamos que tiene la tabla que se muestra en la siguiente figura:

![Ejemplo](../../resources/images/it%20planning_images/groupby-4.png)

A continuación se muestra la ruta de datos utilizada para generar la tabla.

```
docs.org:ABC Company/
Reports/
.DateGoesHere/
CostModels/
Default/
.TableTransform:Data Center Services - Subservice/
.Summary
```

Supongamos que desea agrupar las filas por Servicio y luego por Subservicio. ¡Añade el!GROUPBY a la ruta de datos como se muestra a continuación.

```
docs.org:ABC Company/
Reports/
.DateGoesHere/
CostModels/
Default/
.TableTransform:Data Center Services - Subservice/
!GROUPBY[Service,SubService]/
.Summary
```

El resultado se muestra en la siguiente figura. Observe que las entradas de la columna Centro de datos muestran ahora {Various}. Esto indica que hay dos o más valores de centros de datos para cada fila. En nuestro ejemplo, serían Seattle y Chicago. De nuevo, Apptio añade una columna Count. Tabla después de agrupar por Servicio y Subservicio:

![agrupación por Servicio y Subservicio](../../resources/images/it%20planning_images/groupby-5.png)

Puede realizar este tipo de GROUPBY utilizando la **cinta de opciones** :

1. Seleccione la tabla que desea agrupar.
2. Seleccione la pestaña **Datos** en la **cinta de opciones**.
3. Seleccione el icono **Agrupar** y seleccione el campo o campos que se utilizarán para la agrupación.

## !GROUPBY[nombre columna|nombre columna]

Inherente a Apptio es la posibilidad de desglosar los informes hasta niveles sucesivos de detalle haciendo clic en los enlaces. Al desglosar, lo que hace es filtrar un informe por el enlace seleccionado. ¡Esta versión del!La función GROUPBY comprueba si la ruta de datos se ha filtrado por una columna determinada debido a un desglose. Si no lo ha hecho, agrupa por la primera columna de la lista. En caso contrario, comprueba la siguiente columna de la lista. Si las filas se agrupan por la primera columna, se ignora la segunda.

Esto puede ser útil cuando se combina con informes que se guardan para aplicar "Aunque se filtren de otra manera". Tenga en cuenta que esta sintaxis no se puede utilizar en la práctica con algunos componentes de gráficos, concretamente los componentes que requieren que especifique el nombre de la columna Eje X. Esta funcionalidad aún no se ha generalizado.

**Ejemplo**

La tabla que se muestra en la siguiente figura se ha filtrado por Centro de Datos como resultado de un desglose.

![Filtrado por centro de datos](../../resources/images/it%20planning_images/groupby-6.png)

A continuación se muestra la ruta de datos de la tabla.

```
docs.org:ABC Company/
Reports/
.TableTransform:Data Center Service - Subservice/
!FILTER[{Data Center}="Seattle"]/
.Summary
```

Ahora modifique la ruta de datos como se muestra a continuación para agrupar los resultados por Centro de Datos si aún no se han filtrado, o por Servicio si se han filtrado.

```
docs.org:ABC Company/
Reports/
.DateGoesHere/
CostModels/
Default/
.TableTransform:Data Center Services - Subservice/
!FILTER[{Data Center}="Seattle"]/
!GROUPBY[Data Center|Service]/
.Summary
```

El resultado se muestra en la siguiente figura:

![Resultado](../../resources/images/it%20planning_images/groupby-7.png)

Si tomamos la tabla original sin filtrar que se muestra en la Figura G y aplicamos el mismo datapath, obtenemos el resultado que se muestra en la siguiente figura. Tabla sin filtrar:

![](../../resources/images/it%20planning_images/groupby-8.png)

Tabla sin filtrar agrupada por Centro de Datos:

![Tabla sin filtrar agrupada por Centro de Datos](../../resources/images/it%20planning_images/groupby-9.png)

**Tema principal:** [Tablas editables: Adaptación a las entradas del usuario](../../studio/data_studio/editabletables.html "Se aplica a: TBM Studio 12.6 y posteriores")
