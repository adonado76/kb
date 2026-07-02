---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función superior"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/upper.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función superior

Convierte la cadena de entrada a todos los caracteres en mayúsculas.

## Sintaxis

`Upper(expression)`

## Parámetros

*expresión* : El texto a convertir a mayúsculas. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio

## Comportamiento

- Toma una cadena de entrada y convierte todos los caracteres alfabéticos a sus equivalentes en mayúsculas.
- Los caracteres no alfabéticos (por ejemplo, números, símbolos) se devuelven sin cambios.
- Si la entrada ya está en mayúsculas, se devuelve la cadena original.

## Tipo de retorno

Serie

## Ejemplos

| Ejemplo de función | Valor de retorno |
| --- | --- |
| =Upper("HWbudget" ) | HWBUDGET |
| =Superior( "hwBudget" ) | HWBUDGET |

Nota: Útil para estandarizar entradas de texto para comparaciones que no distinguen mayúsculas de minúsculas o para un formato consistente.
