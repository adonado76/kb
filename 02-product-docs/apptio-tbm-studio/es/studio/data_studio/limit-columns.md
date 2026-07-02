---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Columnas_limitadas"
breadcrumb: []
source_path: "studio/data_studio/limit-columns.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Columnas_limitadas

Determina las columnas que se muestran en una tabla. Puede limitar las columnas mediante la **cinta de opciones**.

## Sintaxis

`!LIMIT_COLUMNS[{columns to include}][{columns to
add}][{columns to exclude}][options]`

## Argumentos

Columnas que deben incluirse
:   Una lista separada por comas de las columnas que se incluirán en la tabla. Es el único argumento obligatorio, pero puede estar vacío. Si está vacío, se incluirán todas las columnas de la tabla.

    Puede utilizar texto dinámico para hacer referencia a una columna de una tabla que sea una lista de columnas separadas por comas. Por ejemploLimit\_Columns[<%=ABC Aggregation.Columns %>] insertaría la lista de columnas en una columna llamada Columns en una tabla llamada ABC Aggregation.

Columnas a añadir
:   Una lista de columnas separadas por comas para añadir a la tabla. Las columnas deben proceder del conjunto de datos utilizado para generar la tabla.

Columnas a excluir
:   Una lista separada por comas de las columnas que se excluirán de la tabla.

## Opciones

Existen las siguientes opciones:

| Opción | Descripción |
| --- | --- |
| máximo:# | Establece el número máximo de columnas que se mostrarán. |
| onlyModeledMetrics | Si la tabla que se está limitando tiene columnas métricas, exclúyalas de la tabla. Mostrar sólo columnas de métricas modeladas. |
| includePrimaryKey | Incluya siempre la columna Clave primaria independientemente de los demás ajustes. |
| showIrrelevant | Anula el filtro de columna correspondiente. |

## Ejemplo

Suponga que tiene la siguiente tabla.

![](../../resources/images/it%20planning_images/limit-columns.png)

La ruta de datos para la tabla es:

```
docs.org:ABC Company/
Reports/
.DateGoesHere/
CostModels/
Default/
.TableTransform:Applications/
.Summary/
!LIMIT[0,2147483647]/
!LIMIT_COLUMNS[]/
```

Sólo desea mostrar las columnas Aplicación, Nivel de servicio y Nivel de soporte. ¡Edita el!LIMIT\_COLUMNS para que tenga el siguiente aspecto:

`!LIMIT_COLUMNS[{Application},{Service Level},{Support Tier}]/`

## Cinta

Para limitar las columnas mostradas mediante la **cinta de opciones** :

1. Seleccione la tabla que desea editar.
2. Seleccione el icono **Propiedades** de la pestaña **Creación de** la **cinta de opciones**.
3. En la pestaña **Datos** del cuadro de diálogo **Propiedades**, utilice los campos **Incluir** o **Excluir** para seleccionar las columnas mostradas.

**Tema principal:** [Tablas editables: Adaptación a las entradas del usuario](../../studio/data_studio/editabletables.html "Se aplica a: TBM Studio 12.6 y posteriores")
