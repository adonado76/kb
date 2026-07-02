---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Concatenación de cadenas"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/string-concatenation.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Concatenación de cadenas

**Se aplica a** : TBM Studio 12.0 y posteriores

Para dar formato a los valores de las métricas, puede especificar una cadena en una expresión.

El siguiente ejemplo pone un signo de dólar ( $ ) delante del valor de la columna Coste. Si Coste es 200, esta expresión se evalúa a 200 $.

`="$"+Cost`

El ejemplo anterior también podría escribirse con un ampersand ( & ) como operador de concatenación, como se muestra en el siguiente ejemplo.

`="$"&Cost`

El siguiente ejemplo antepone el valor de la columna Descripción del billete al valor de la columna Número de billete, que está entre paréntesis. Si Billete

La descripción es Hardware y el número de ticket es 10065, esta expresión se evalúa como Hardware(10065).

```
=Ticket
            Description&"("&Ticket Number&")"
```

Nota: Aunque se puede utilizar el signo más ( + ) o el ampersand ( & ) para concatenar cadenas, la mejor práctica es utilizar el ampersand.

## Uso de guiones

Al concatenar texto, puede representar los guiones con un doble ampersand (&&). A menudo se utiliza para crear claves únicas para las entradas del libro mayor. Si un elemento a concatenar está en blanco, no lo incluirá en la concatenación.

Por ejemplo, si introduce esta cadena

`string1&&string2&&string3`

Se traducirá como:

`string1 - string3`

Tenga en cuenta que && pone un espacio antes y después del guión.

## Ejemplo

Caso 1: Se añade un espacio entre 2 &&'s

="A"&&" "&&"B" se traducirá como A - - B

Caso 2: Se añade un valor nulo o "" entre 2 &&'s

="A"&&""&&"B" se traducirá como A - B

Caso 3: No se añade "" entre 2 && dará lugar a error

="A"&&&&"B" se traducirá como ERROR
