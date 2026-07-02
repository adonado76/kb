---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función de suma"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/sum.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función de suma

Devuelve la suma total de los valores de la columna numérica especificada.

## Sintaxis

`Sum(column)`

## Argumentos

*columna* : La columna numérica a sumar. Opcional

## Tipo de retorno

Número

## Ejemplos

La siguiente tabla muestra los resultados cuando la columna Suma contiene la función =Suma(Valor):

| Grupo | Valor | Suma |
| --- | --- | --- |
| A | 4 | 108 |
| A | 8 | 108 |
| B | 19 | 108 |
| B | 16 | 108 |
| B | 23 | 108 |
| C | 42 | 108 |

La siguiente tabla agrupada muestra los resultados cuando la columna Suma contiene la función =Suma(Valor):

| Grupo | Valor | contar | Suma |
| --- | --- | --- | --- |
| A | 6 | 2 | 108 |
| B | 54 | 3 | 108 |
| C | 42 | 1 | 108 |

## Posibles resultados engañosos

La función Suma puede dar lugar a resultados técnicamente correctos pero engañosos. Por ejemplo, suponga que tiene la siguiente tabla:

| Centro de datos | Número ofServers | Coste total | Coste por servidor |
| --- | --- | --- | --- |
| Este | 1 | 100 dólares | 100 dólares |
| Oeste | 4 | 200 dólares | 50 dólares |
| Total | 5 | 300 dólares | 60 dólares |

La columna Coste por servidor se calcula dividiendo el coste total por el número de servidores. El valor de Coste por servidor en la fila Total también se calcula basándose en 5 servidores con un coste total de 300 $: 300 $/5 = 60 $.

Si utiliza la función Suma para la columna Coste por servidor, obtendrá el siguiente resultado:

| Centro de datos | Número ofServers | Coste total | Coste por servidor |
| --- | --- | --- | --- |
| Este | 1 | 100 dólares | 300 dólares |
| Oeste | 4 | 200 dólares | 300 dólares |
| Total | 5 | 300 dólares | 60 dólares |

`Sum(Cost)` : Devuelve el total de todos los valores de la columna {Cost}.
