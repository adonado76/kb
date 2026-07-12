---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Análisis mejorado de Excel"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Data Studio Referencia"
source_path: "studio/new-uc/reference/enhanced-excel-parsing.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Análisis mejorado de Excel

El análisis mejorado de Excel lee los valores sin formato directamente de los archivos de Excel, sin tener en cuenta el formato de Excel, lo que garantiza una mayor precisión.

## Gestión de formatos

|  |  |  |  |
| --- | --- | --- | --- |
| **Formato de Excel** | **Antiguo analizador sintáctico** | **Nuevo analizador** | **Fórmula de conversión** |
| Tema general | Hola | Hola | No es necesario |
| Número | 1 | 0.99999999 | =Round( {Column},0) |
| Moneda | $10.50 | 10.5 | =Moneda( {Column}, "#,## 0.00 ") |
| Gestión de Cuentas | 34, 343.00 | 34343 | =NumberFormat({Column},"#,##0.00") |
| Fecha | 1-Jan-24 | 1704047400 (época) | =DateFormat({Column }, "d-MMM-aaaa") |
| Porcentaje | 10 % | 0.1 | =NumberFormat({Column }, "#.00%") |

## Conversión de fecha y hora

**Sistema de fechas de Excel:** números de serie secuenciales que comienzan por 1 = 1 de enero de 1900

**Unix Periodo:** Comienza el 1 de enero de 1970, a las 00:00:00 UTC

**Fórmula de conversión:** =DateFormat(({Column }-25569)\*86400,"M/d/aa")

**Explicación:**

- 25569 = días transcurridos entre la época de Excel (1900) y la época de « Unix » (1970)
- 86 400 = segundos al día

**Tema principal:** [Referencia de « Data Studio »](../../../studio/new-uc/reference/data-studio-reference.html)
