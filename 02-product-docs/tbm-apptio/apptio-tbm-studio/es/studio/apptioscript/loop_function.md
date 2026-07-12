---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función de bucle"
breadcrumb: []
source_path: "studio/apptioscript/loop_function.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función de bucle

Utilice la función Bucle para recorrer un conjunto de datos sin procesar y ejecutar sentencias para cada fila del conjunto de datos.

## Sintaxis

```
Loop data set
statements
End Loop
```

## conjunto de datos

El conjunto de datos.

## declaraciones

Las sentencias que desea ejecutar para cada fila del conjunto de datos.

## Ejemplo

El siguiente ejemplo imprime Coste = y el valor de Coste para cada fila del conjunto de datos llamado mydatasetname.

```
Loop mydatasetname
Debug("Cost=" Cost)
End Loop
```
