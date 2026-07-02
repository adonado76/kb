---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Todas las opciones de configuración de asignación"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia del estudio de modelos"
  - "Asignaciones"
source_path: "studio/new-uc/reference/model-studio-reference/allocation-config.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Todas las opciones de configuración de asignación

Esta tabla recoge todas las opciones de configuración para todos los tipos de asignación.

**Referencia completa de parámetros**

|  |  |  |
| --- | --- | --- |
| **Parámetro** | **Se aplica a** | **Descripción** |
| Asignar | Todos los tipos | Selecciona las métricas que deseas asignar (coste, presupuesto, etc.) |
| Uso de | Todos los tipos | Selección del tipo de asignación |
| Para | Todos los tipos | Objeto del modelo de destino |
| Distribución | Ponderado, Consumo, Estándar, Recursión | Igual, Por peso o Relación de datos |
| Peso por | Cuando la distribución = peso por | Columna de la tabla, métrica u otro factor determinante |
| Relación entre datos | Cuando la distribución equivale a la relación entre datos | Pares de columnas de origen y destino |
| Columna de consumo | Solo para consumo | Columna «Objetivo» que muestra las unidades consumidas |
| Columna de capacidad | Solo para consumo | Columna «Fuente» que muestra la capacidad total |
| Fórmula | Solo fórmula | Fórmula de asignación personalizada |
| Precisión | Solo recursividad | Valor mínimo para continuar con la iteración |
| Número máximo de iteraciones | Solo recursividad | Número máximo de ciclos de asignación |
| Modo incremental | Solo recursividad | Añade el valor de iteración a la fuente |
| Desde el filtro | Fórmula | Filtrar filas en la tabla de origen |
| Para filtrar | Fórmula | Filtrar filas en la tabla de destino |

**Tema principal:** [Asignaciones](../../../../studio/new-uc/reference/model-studio-reference/allocations.html)
