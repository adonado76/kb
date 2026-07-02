---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "es"
doc_type: "it-benchmarking"
title: "Elementos comunes en las vistas de benchmarking"
breadcrumb:
  - "Benchmarking"
  - "Informes comparativos"
source_path: "it-benchmarking/benchmarking-reports/common-elements-benchmarking-views.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Elementos comunes en las vistas de benchmarking

Una vez que comprendas las piezas comunes, cada vista se vuelve más fácil.

**Filtros y selección de pares**   
 Casi todas las vistas de Benchmarking tienen filtros o vistas segregadas para:

- Industria o sector
- Rango de tamaño (normalmente ingresos o número de empleados)
- Región o geografía

Siempre deberías poder completar esta frase:   
«Este gráfico nos compara con [sector], [región], [rango de tamaño], para el año fiscal [N]»

Si no puede, deténgase y corrija los filtros antes de presentar nada.

**Puntos de referencia y posiciones**   
Los puntos de referencia suelen mostrarse como diagramas de caja:

- Un punto o línea central para la mediana
- Una banda para el rango intercuartílico (percentil 25 al 75)
- A veces, bigotes o líneas para los valores mínimo y máximo
- Una línea discontinua o un marcador especial que represente a su organización

![Diagrama de caja interactivo de benchmarking](../../resources/images/it%20benchmarking_images/interactive-benchmarking-box-plot.png)

  
Leyendo esto:

- La mediana te indica «el punto medio»
- La banda te dice cómo es lo «más o menos normal»
- Tu marcador te indica si estás por debajo, en la media o por encima en comparación con tus compañeros

  
«Alto» no es automáticamente malo; es simplemente donde te encuentras.

**Desglose y detalle** La mayoría  
 de los informes de costes habilitados para Benchmark admiten alguna versión de desglose:

- Desde el gasto total en TI hasta el gasto por torre de recursos o grupo de costes
- Desde una torre de recursos atípica hasta grupos de costes, proveedores o servicios
- Desde una diferencia de referencia en los informes de costes hasta las cuentas o los factores determinantes

![Resumen de costes de infraestructura del proyecto con desglose detallado para la torre de recursos «Compute».](../../resources/images/it%20benchmarking_images/drill-resourse-tower.png)

  
El flujo de trabajo general es el siguiente:

- Detecta una brecha en una vista de referencia.
- Analiza tus datos internos hasta que puedas ver qué los impulsa.
- Decida si se trata de un problema de alcance, una elección de diseño o una oportunidad real de optimización.
