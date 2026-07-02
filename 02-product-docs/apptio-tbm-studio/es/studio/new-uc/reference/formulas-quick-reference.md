---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Referencia rápida de fórmulas"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Data Studio Referencia"
source_path: "studio/new-uc/reference/formulas-quick-reference.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Referencia rápida de fórmulas

Para consultar la documentación completa sobre fórmulas y funciones, véase la sección «Fórmulas y funciones de 5.4 ». Añadir pasos de transformación

**Sintaxis de la fórmula:**

- Empieza con = (obligatorio)
- Columnas de referencia con llaves: {Column Name}
- Utiliza los operadores estándar: +, -, \*, /

**Patrones comunes en fórmulas:**

|  |  |
| --- | --- |
| **Patrón** | **Ejemplo de fórmula** |
| Concatenar | ="prefijo-"& {Column} |
| Condicional | =Si( {Type} ="A", {Value} \*2, {Value} ) |
| Búsqueda | =BUSCAR( {Key}, Tabla, {SourceKey}, {ReturnColumn} ) |
| Formato de número | =NumberFormat({Column},"#,###") |
| Conversión de tipo (de cadena a numérico) | =VALOR( {Column} ) |
| Conversión de tipos (de numérico a etiqueta) | =NumberFormat({Column},"#,###") |
| Formato de fecha | =DateFormat({Column ), "aaaa-MM-dd") |

**Tema principal:** [Referencia de « Data Studio »](../../../studio/new-uc/reference/data-studio-reference.html)
