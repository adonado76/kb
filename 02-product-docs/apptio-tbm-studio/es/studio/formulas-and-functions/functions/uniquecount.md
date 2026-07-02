---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "UniqueCount función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/uniquecount.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# UniqueCount función

**Se aplica a** : TBM Studio 12.0 y posteriores

Devuelve un recuento de valores distintos en una columna.

## Dónde utilizarlo

Esta función puede utilizarse en:

- Conjuntos de datos
- Columnas de fórmulas en tablas de informes

Nota: Esta función no puede utilizarse en la mesa en la que se aplicará. Por ejemplo, no puede crear una fórmula como =UniqueCount(Servers:Location ) en la tabla Servidores.

## Sintaxis

UniqueCount(table nombre:columna)

## Argumentos

*nombre de la tabla*

La tabla que se examinará en busca de valores distintos.

*columna*

La columna que se examinará en busca de valores distintos. Tenga en cuenta que se utilizan dos puntos entre el nombre de la tabla y el de la columna. Por ejemplo: Servidores:Ubicación.

## Tipo de retorno

Número

## Ejemplo

Suponga que tiene la siguiente tabla:

| Servidor | Ubicación |
| --- | --- |
| EXCH006 | Seattle |
| EXCH010 | Boston |
| NET207 | Boston |
| STOR124 | Seattle |
| STOR250 | Boston |
| STOR350 | Denver |

La siguiente función, si se ejecuta contra la tabla Servidores anterior, devuelve 3, porque la tabla contiene 3 ubicaciones distintas.

=UniqueCount(Servers:Location)

**Véase también** : [RowCount](rowcount.htm "(se abre en una pestaña o una ventana nueva)")
