---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Función izquierda"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/left.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Función izquierda

Devuelve un número determinado de caracteres de una cadena (incluidos los espacios en blanco), empezando por la izquierda.

## Sintaxis

`Left(string, count)`

## Parámetros

*cadena* : La cadena de la que extraer los caracteres. También puede utilizar una referencia de columna. Nota: Este parámetro acepta una expresión, lo que significa que puede proporcionar un valor literal, una referencia de columna o el resultado de otra función. Obligatorio

*count* : El número de caracteres a devolver desde la izquierda. Si el valor es una cadena, se convertirá en un número. Si la conversión falla, el valor por defecto es 0. Opcional (por defecto: 1)

## Comportamiento

Extrae caracteres del principio de la cadena de entrada en función del recuento. Si no se especifica count, se devuelve 1 carácter.

## Tipo de retorno

Serie

## Ejemplos

- Left("Seattle", 3): Devuelve 'Sea'.
- Izquierda(Nombre, 1): Devuelve el primer carácter de la columna 'Nombre'.
- Left("Ubicación"): Devuelve 'L' ya que no se proporciona ningún recuento y el valor por defecto es 1.

| Ejemplo de función | Valor de retorno |
| --- | --- |
| =Izquierda("123456",3) | 123 |
| =Izquierda("123456",1) | 1 |
| =Izquierda("123456") | 1 |
| =Izquierda("Me gusta la tarta.",6) | Me gusta |
| =Izquierda("Me gusta la tarta.") | I |
