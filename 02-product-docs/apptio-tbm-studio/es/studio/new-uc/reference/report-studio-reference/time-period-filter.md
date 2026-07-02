---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Filtrado por periodo"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: filtros y segmentadores"
source_path: "studio/new-uc/reference/report-studio-reference/time-period-filter.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Filtrado por periodo

**Funcionalidad del selector de fechas**

Aunque TBM Studio no cuenta con un componente específico para seleccionar fechas, puedes crear una función de selección de fechas utilizando los selectores de columna o los botones.

**Opción 1: Selector de columnas como selector de fechas**

1. Añadir un selector de columnas al informe
2. Configurar con valores basados en el tiempo desde la perspectiva «Tiempo»
3. Configurar en modo de selección única

Los usuarios pueden elegir entre opciones como «Mes actual», «Trimestre actual», «Semestre actual» o «Acumulado en lo que va de año».

**Configuración del periodo de datos**

En los gráficos y las tablas, la opción «Período de datos» determina qué datos del período se muestran:

|  |  |
| --- | --- |
| **Valor** | **Comportamiento** |
| Fecha actual del proyecto (por defecto) | Muestra los datos correspondientes a la fecha seleccionada en el selector de fechas del encabezado del informe |
| Inicio del ejercicio fiscal actual | Cierre del primer periodo del ejercicio fiscal actual |
| Inicio del trimestre fiscal actual | Cierre de la primera fase del trimestre actual |
| Fecha específica | Se limita a un período especificado explícitamente |

Nota: Para crear gráficos de tendencias que muestren todo el ejercicio fiscal, independientemente del período actual, configure el «Período de datos» en «Inicio del ejercicio fiscal actual»

**Tema principal:** [Componentes de los informes: Filtros y segmentadores](../../../../studio/new-uc/reference/report-studio-reference/report-component-filters-slicers.html)
