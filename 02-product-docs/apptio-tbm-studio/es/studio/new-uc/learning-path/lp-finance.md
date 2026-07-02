---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Itinerarios de formación para equipos de TI y finanzas"
breadcrumb:
  - "TBM Studio"
  - "Itinerarios de aprendizaje (basados en funciones)"
source_path: "studio/new-uc/learning-path/lp-finance.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Itinerarios de formación para equipos de TI y finanzas

**Objetivo:** modelar con precisión los costes de TI, crear reglas de asignación y fomentar la transparencia financiera de los servicios de TI

**A quién va dirigido:** Directores financieros de TI, analistas financieros responsables de los modelos de costes de TI y cualquier persona que elabore y mantenga modelos de asignación de costes

## Introducción (30 minutos)

**Lo que** aprenderás: la metodología TBM y los conceptos básicos del modelado

**Objetivos de aprendizaje:**

- Comprender la metodología y el marco de trabajo de TBM
- Aprende los conceptos clave: grupos de costes, imputaciones, «showback» frente a «chargeback»
- Comprender el flujo de trabajo «de los datos al modelo y al informe»
- Navegar por la interfaz de Model Studio
- Saber cuándo utilizar los distintos métodos de asignación

**Temas que hay que completar:**

1. Descripción general de la metodología TBM (10 min)
2. [Conceptos básicos del modelado](../getting-started/core-concepts.html) (10 min)
3. [Visita rápida al modelo](../getting-started/qsg.html) (10 min)

**Requisitos previos:** Conocimientos básicos sobre las estructuras de costes de las tecnologías de la información y conceptos financieros

## Habilidades básicas (4 horas)

**Lo que** aprenderás: cargar datos, elaborar modelos de costes, crear asignaciones y verificar la precisión

**Objetivos de aprendizaje:**

- Cargar y preparar los datos de costes para la modelización
- Crear modelos básicos de asignación de costes
- Crea reglas de asignación utilizando los factores determinantes adecuados
- Verificar la precisión del modelo y conciliar los totales
- Comprender los cálculos del modelo y los plazos

**Temas que hay que completar:**

1. [Cargar y preparar los datos](../howtoguides/work-with-data/data-import-mgmt.html) (45 min)
2. [Transformar datos para el modelado (45 min)](../howtoguides/work-with-data/transform-enrich-data.html)
3. [Crear modelos básicos de costes](../howtoguides/build-cost-model/model-basics.html) (60 min)
4. [Crear asignaciones sencillas](../howtoguides/build-cost-model/setup-sa.html) (45 min)
5. Validar la precisión del modelo (30 min) *→ Sección 3.2.4*
6. Comprender la estructura y el cálculo (15 min) *→ Sección 4.5*

**Requisitos previos:** haber completado el curso básico y tener acceso a los datos de costes

**Tiempo estimado para la práctica:** añade entre 3 y 4 horas trabajando con datos de ejemplo o un modelo piloto

## Avanzado (6 horas)

**Lo que aprenderás** : Dominar las asignaciones complejas, los modelos de varios niveles, la elaboración de presupuestos y la optimización avanzada de modelos

**Objetivos de aprendizaje:**

- Diseñar e implementar flujos de asignación complejos de varios niveles
- Gestionar escenarios de asignación complejos (en cascada, ponderada, condicional)
- Elabora modelos presupuestarios y de previsión junto con los datos reales
- Realizar análisis hipotéticos y modelización de escenarios
- Optimizar el rendimiento de los modelos y los tiempos de compilación
- Aplicar las mejores prácticas en materia de asignación

**Temas que hay que completar:**

1. [Flujos de costes de varios niveles](../howtoguides/build-cost-model/create-multi-tier-allo.html) (90 min) *→ Sección 3.2.3*
2. [Patrones avanzados de asignación](../howtoguides/build-cost-model/create-multi-tier-allo.html) (60 min) *→ Sección 3.2.3*
3. [Modelización de presupuestos y previsiones](../howtoguides/build-cost-model/understand-model-metrics.html) (60 min) *→ Sección 3.2.5*
4. **Análisis de hipótesis** (45 min) *→ Sección 3.2.6*
5. [Optimización del rendimiento de los modelos](../admin/performance-optimize.html) (45 min)
6. [Modelo de gobernanza y mejores prácticas](../admin/project-admin.html) (30 min) *→ Sección 6.1*

**Requisitos previos:** haber completado el curso «Habilidades básicas» y tener experiencia en la creación de modelos sencillos

## Retos habituales

- **Costes no asignados:** Revisar la integridad de los datos de los conductores y la lógica de correspondencia
- **Asignaciones circulares:** rediseñar el flujo del modelo o utilizar el método recíproco
- **Rendimiento de la compilación:** simplificar las transformaciones, reducir el alcance de los cálculos
- **Calidad de los datos:** aplicar reglas de validación en las primeras fases del proceso
