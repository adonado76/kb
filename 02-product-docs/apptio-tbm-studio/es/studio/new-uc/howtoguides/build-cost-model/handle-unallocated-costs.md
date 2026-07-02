---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Gestionar los costes no asignados"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Crear modelos de costes"
  - "Crear asignaciones"
source_path: "studio/new-uc/howtoguides/build-cost-model/handle-unallocated-costs.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Gestionar los costes no asignados

**Objetivo:** Gestionar los costes que no se ajustan a los criterios de asignación para garantizar que el 100 % de los costes se reflejen en el modelo.

**Cuándo utilizarlo:** tras ejecutar las asignaciones, quedan costes que no se han distribuido a las tablas de destino. Esto suele ocurrir cuando los criterios de coincidencia de controladores no abarcan todas las filas de origen.

**Tiempo estimado:** entre 15 y 30 minutos, dependiendo de la estrategia elegida

## Comprender los costes no asignados

Los costes no asignados se producen cuando:

- Las filas de origen no coinciden con ninguna fila de destino (no hay valores de clave coincidentes)
- Los filtros excluyen determinadas filas de origen de todas las asignaciones
- Los valores de ponderación son cero en algunas filas de destino
- Se reciben nuevos datos que no se habían previsto en el diseño original de la asignación

## Estrategia 1: Crear un fondo de reserva

Un fondo residual es un destino genérico al que se asignan los costes que no se ajustan a ningún criterio de asignación específico.

**Cuándo utilizarlo: cuando** se desea realizar un seguimiento por separado de los costes no asignados con fines de análisis, al tiempo que se garantiza el equilibrio del modelo.

**Pasos**

1. **Crear una mesa de billar residual**
   - En Data Studio, cree una nueva tabla llamada «Costes no asignados» o «Fondo residual».
   - Añade la tabla al modelo mediante un paso de modelo.
2. **Crear una asignación genérica**
   - En la tabla de origen, crea una nueva asignación después de todas las asignaciones específicas.
   - No añadas ningún filtro (esto captura todo lo que queda).
   - Establecer el peso por = Par.
3. **Supervisar el fondo de reserva**
   - Revisa periódicamente los importes residuales del fondo común.
   - Las cantidades elevadas indican problemas de coincidencia o de calidad de los datos.

## Estrategia 2: Distribución equitativa de los costes restantes

Distribuye los costes no asignados de manera uniforme entre los objetivos existentes, en lugar de contabilizarlos por separado.

**Cuándo utilizarlo: cuando** los costes no asignados son reducidos o resulta aceptable repartirlos proporcionalmente entre todos los destinatarios.

- Crea una asignación en dos pasos: primero con una asignación específica y, a continuación, con una distribución equitativa del resto.
- Añade un filtro «De» en la segunda asignación para seleccionar solo las filas sin emparejar.

## Estrategia 3: Distribución proporcional mediante ponderación métrica

Distribuye los costes no asignados de forma proporcional, basándote en cómo se han asignado ya los demás costes.

**Cuándo utilizarlo:** cuando se desea que los costes no asignados sigan el mismo patrón de distribución que los costes asignados.

- Crea una asignación secundaria con «Ponderación por» = «Métrica».
- Selecciona la métrica de tu asignación principal.
- De este modo, los costes restantes se reparten utilizando las mismas proporciones.

## Estrategia 4: Abordar la causa raíz

Elimine los costes no asignados resolviendo los problemas subyacentes relacionados con los datos o la configuración.

1. **Identificar por qué hay costes sin asignar**
   - Exporta las filas no asignadas de la vista previa.
   - Analiza los valores de las claves de correspondencia.
2. **Solucionar los problemas de calidad de los datos**
   - Si las claves están mal escritas o son incoherentes, corrígelas en los datos de origen o en las transformaciones.
   - Si aparecen nuevas categorías, añádelas a la tabla de destino.
3. **Actualizar la lógica de coincidencia**
   - Si los criterios de búsqueda son demasiado restrictivos, amplíalos.
   - Añade relaciones de datos adicionales si es necesario.

## Matriz de decisión sobre costes no asignados

|  |  |
| --- | --- |
| **Situación** | **Estrategia recomendada** |
| Importe elevado sin asignar (>5 % del total) | Solucionar la causa principal |
| Pequeña cantidad no asignada (<5 % del total) | Distribución proporcional o fondo de reserva |
| Se necesita un registro de auditoría para los fondos no asignados | Fondo residual |
| Un problema puntual con los datos | Distribución equitativa entre los destinatarios actuales |
| Abonos o anulaciones que dan lugar a saldos negativos | Separar y manipular por separado |

**Tema principal:** [Crear asignaciones](../../../../studio/new-uc/howtoguides/build-cost-model/create-allocation.html)
