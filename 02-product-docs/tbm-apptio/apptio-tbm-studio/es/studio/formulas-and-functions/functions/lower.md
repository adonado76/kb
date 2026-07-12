---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función inferior"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/lower.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función inferior

Convierte la cadena de entrada a minúsculas. caracteres

## Sintaxis

`Lower(expression)`

## Parámetros

*expresión* : El texto a convertir a minúsculas. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio

## Comportamiento

- Toma una cadena de entrada y convierte todos los caracteres alfabéticos a sus equivalentes en minúsculas.
- Los caracteres no alfabéticos (por ejemplo, números, símbolos) se devuelven sin cambios.
- Si la entrada ya está en minúsculas, se devuelve la cadena original.

## Tipo de retorno

Serie

## Ejemplos

| Ejemplo de función | Valor de retorno |
| --- | --- |
| =Menor("Presupuesto para tareas") | presupuesto de hardware |
| =Lower( "hwBudget" ) | presupuesto de hardware |
| Inferior("Finanzas") | finanzas |
| Inferior( {Department Name} ) | Convierte todos los valores de la columna {Department Name} a minúsculas. |

Nota: Útil para estandarizar entradas de texto para comparaciones que no distinguen mayúsculas de minúsculas o para un formato consistente.
