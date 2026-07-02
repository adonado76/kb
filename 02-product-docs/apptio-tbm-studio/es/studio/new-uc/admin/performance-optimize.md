---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Rendimiento y optimización"
breadcrumb:
  - "TBM Studio"
  - "Administración"
source_path: "studio/new-uc/admin/performance-optimize.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Rendimiento y optimización

**Tipo de contenido:** Guía práctica / Solución de problemas

**Destinatarios:** Administradores, usuarios avanzados

**Requisitos previos:** rol de administrador o de usuario avanzado, conocimiento de la estructura del modelo

La optimización del rendimiento es fundamental para garantizar que los informes respondan con rapidez y que los cálculos se realicen de forma eficiente. En esta sección se describen las herramientas y las prácticas recomendadas para supervisar y mejorar el rendimiento de TBM Studio.

## Calc Explorer

Calc Explorer ofrece información detallada sobre los procesos de cálculo y ayuda a identificar los cuellos de botella en el rendimiento. Muestra el esfuerzo de cálculo para informes, transformaciones, desgloses y métricas.

**Para acceder a Calc Explorer:**

- Ve a **«Build» > «Calc Explorer»**
- Selecciona una compilación para analizar los detalles de su cálculo
- Ver informes, transformaciones, desgloses y métricas cuyo cálculo tardó más de 10 segundos

**Nota:** *Calc Explorer solo registra los elementos cuyo cálculo tarda más de 10 segundos. Los componentes que se completan rápidamente no aparecerán en el análisis.*

## Detección de anomalías en la compilación

La función de detección de anomalías identifica cambios inusuales en el esfuerzo de cálculo, lo que te ayuda a detectar a tiempo posibles problemas de rendimiento. Compara cada compilación con las anteriores y te avisa de los cambios significativos.

**Tipos de anomalías detectadas:**

- **Anomalía en el cálculo** : aumento inesperado del tiempo de cálculo
- **Anomalía basada en entidades** : patrones inusuales en la estructura de los datos (por ejemplo, recuentos de filas inesperados)
- **Combinado** : se detectan conjuntamente tanto las anomalías de cálculo como las basadas en entidades

**Para habilitar la detección de anomalías:**

- Ve a **Proyecto > Activar funciones**
- Selecciona **«Mostrar panel de anomalías»**
- Ver anomalías en **Proyecto > Anomalías**

## Motor de recomendaciones

El motor de recomendaciones identifica problemas de configuración que pueden afectar al rendimiento o a la calidad de los datos. Ofrece flujos de trabajo guiados para resolver problemas habituales.

**Tipos de recomendaciones habituales:**

- **Asignaciones de cero unidades** : asignaciones con cero unidades que consumen tiempo de procesamiento sin aportar ningún valor
- **Asignaciones no utilizadas** : etapas de asignación que ya no son necesarias
- **Informes no utilizados** : informes a los que no se ha accedido recientemente
- **Columnas de datos de las** tablas base no utilizadas: columnas de las tablas base que no se utilizan en las transformaciones ni en los informes
- **Problemas con ALL\_ROWS** : consultas basadas en el tiempo que pueden requerir el manejo de ALL\_ROWS

**Para dar curso a las recomendaciones:**

- Ve a **TBM Studio > Recomendaciones**
- Selecciona una recomendación y haz clic en **«Solucionar todos los problemas detectados»**
- Sigue el proceso guiado para revisar y solucionar los problemas
- Confirmar los cambios cuando haya terminado

## Componente de evaluación del rendimiento

El componente «Análisis del rendimiento» ofrece informes que ayudan a los administradores a comprender el impacto de la configuración del proyecto en el rendimiento. Incluye un análisis de las relaciones de asignación, el estado de los identificadores y la granularidad del modelo.

**Informes clave del componente de evaluación del rendimiento:**

- **Información** sobre asignaciones: muestra el tamaño de las tablas de relaciones de asignación para identificar rápidamente las asignaciones de gran tamaño
- **Información sobre consultas de desglose e identificadores** : analiza la granularidad de las tablas y la eficiencia de la asignación
- **Nivel de detalle del modelo** : identifica las áreas en las que las asignaciones de importes reducidos pueden afectar al tiempo de cálculo
- **Puntuación de salud del identificador** : mide la variación del identificador a lo largo del tiempo (escala de 1 a 100)

## Prácticas recomendadas para la optimización del rendimiento

- **Reducir el nivel de detalle innecesario** : eliminar las columnas y los datos que no sean necesarios para las asignaciones o la elaboración de informes
- **Agrupar filas** : agregar datos a nivel de transacción para reducir el número de filas en los casos en que no se necesiten los detalles
- **Desactivar los informes que no se utilizan** : los informes aumentan el tiempo de cálculo aunque no se consulten con frecuencia
- **Sustituye `Eval()` por ` DynamicColumn( `)** - Permite mejorar el rendimiento de los cálculos de precisión
- **Limitar la duración del proyecto** : calcular únicamente los periodos necesarios para cumplir con los requisitos de presentación de informes
- **Aplicar las recomendaciones de forma periódica** : abordar de forma proactiva las asignaciones de cero unidades y las configuraciones no utilizadas
