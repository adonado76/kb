---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Modelo de madurez de TBM"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Fundamentos de la TBM"
source_path: "studio/new-uc/concepts-architecture/tbm-maturity-model.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Modelo de madurez de TBM

El TBM es un camino, no un destino. Las organizaciones suelen pasar por etapas de creciente sofisticación. Saber en qué punto del camino te encuentras te ayuda a establecer expectativas realistas y a planificar tus próximos pasos. El siguiente modelo de madurez ofrece una hoja de ruta.

## Nivel 1: Visibilidad de los costes

**Características**

En esta fase, la organización tiene un conocimiento básico de los costes de TI, pero su capacidad para desglosarlos por servicio o usuario es limitada. Los datos sobre costes están disponibles en los sistemas financieros, pero no están estructurados para el análisis TBM.

**Funcionalidades habituales**

- Se conoce el gasto total en TI a grandes rasgos
- Los costes se pueden clasificar en grandes categorías (hardware, software, mano de obra)
- Asignación limitada o nula de los gastos compartidos
- La presentación de informes se realiza de forma puntual, normalmente en hojas de cálculo

**Funciones de TBM Studio compatibles con este nivel**

- Data Studio para importar y organizar datos financieros procedentes de sistemas de contabilidad general
- Tablas de conversión básicas para la clasificación de costes
- Informes sencillos que muestran el desglose de los costes por categoría

**Señales de que estás listo para dar un paso adelante**

- Dispones de datos coherentes y fiables que se importan a TBM Studio
- Las partes interesadas piden más detalles («¿Qué hay detrás de esa cifra sobre el software?»)
- Ha identificado los factores clave que podrían respaldar la asignación

## Nivel 2: Transparencia en los costes

**Características**

La organización ha implantado un sistema de asignación de costes y puede rastrear los costes de TI a través de los niveles de la taxonomía hasta llegar a los servicios y a los usuarios. Se ha implantado un sistema de informes de reembolso, y las partes interesadas saben en qué se gastan el presupuesto de TI.

**Funcionalidades habituales**

- Asignación completa de costes desde los grupos de costes, pasando por las torres, hasta los servicios y las unidades de negocio
- Se ofrece el cálculo de costes por nivel de servicio
- Los informes de Showback se distribuyen periódicamente
- Se lleva a cabo un seguimiento de la comparación entre los datos presupuestados y los reales

**Funciones de TBM Studio compatibles con este nivel**

- El motor de asignación completo de Model Studio con flujos de varios niveles
- Varias métricas del modelo (coste, presupuesto, previsión)
- Paneles de Report Studio con seguridad a nivel de fila para la elaboración de informes de las unidades de negocio
- Informes de modelos (vistas de Sankey) para la visualización del flujo de costes

**Señales de que estás listo para dar un paso adelante**

- Su modelo de costes ha sido validado y las partes interesadas confían en las cifras
- Las unidades de negocio se preguntan: «¿Cómo podemos reducir nuestros costes?»
- Tienes suficientes datos históricos para realizar un análisis de tendencias

## Nivel 3: Optimización de costes

**Características**

La organización utiliza activamente los datos de TBM para identificar y buscar formas de reducir costes. El análisis de tendencias revela patrones, la evaluación comparativa pone de relieve oportunidades y se realiza un seguimiento y una medición de las iniciativas de optimización.

**Funcionalidades habituales**

- Análisis de tendencias interanuales
- Análisis comparativo interno y externo
- Programas de optimización activos basados en datos de TBM
- Es posible que se apliquen devoluciones para crear incentivos económicos
- Modelización de escenarios hipotéticos para los cambios propuestos

**Funciones de TBM Studio compatibles con este nivel**

- Métricas calculadas para el análisis de la varianza y el cálculo de tendencias
- Tablas publicadas para exportar datos a sistemas financieros (compatibilidad con devoluciones)
- Tablas editables para la planificación de escenarios y el enriquecimiento de datos
- Funcionalidades de desglose para el análisis de las causas fundamentales

**Señales de que estás listo para dar un paso adelante**

- La optimización de costes está generando ahorros cuantificables
- Los directivos se preguntan cuál es el valor empresarial de las inversiones en TI, y no solo su coste
- Dispone de la infraestructura de datos necesaria para vincular los costes de TI con los resultados empresariales

## Nivel 4: Gestión del valor

**Características**

La organización vincula los costes de TI con el valor empresarial. Las decisiones de inversión se basan en los datos de TBM, y el departamento de TI se posiciona como un socio estratégico del negocio, en lugar de como un centro de costes. Los datos de TBM sirven de base para la gestión de la cartera, la priorización de inversiones y la planificación estratégica.

**Funcionalidades habituales**

- Gestión de la cartera de inversiones en TI
- Indicadores de valor empresarial vinculados a los datos de costes de TI
- Apoyo estratégico en la toma de decisiones sobre inversiones en tecnología
- Una cultura de optimización continua arraigada en la organización
- Previsión avanzada y análisis predictivo

**Funciones de TBM Studio compatibles con este nivel**

- Conjunto completo de métricas de modelos, incluidas métricas personalizadas basadas en el valor
- Informes avanzados con métricas calculadas que combinan datos de costes y de negocio
- Integración de API para conectar los datos de TBM con los sistemas de planificación empresarial
- ApptioScript para cálculos personalizados y modelización de valores

**Señales de madurez en este nivel**

- Las decisiones de inversión en TI se basan en datos y están vinculadas a los resultados empresariales
- Las conversaciones de los directores de sistemas de información se centran en la generación de valor más que en la reducción de costes
- Los datos de TBM se integran en los procesos de planificación y estrategia de la empresa

## Resumen del modelo de madurez

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Nivel** | | **Foco** | **Pregunta clave** | **Áreas principales del estudio TBM** |
| **1. Visibilidad** | | Sé consciente de lo que gastas | ¿Cuánto cuesta? | Data Studio, informes básicos |
| **2. Transparencia** | | Comprender el flujo de los costes | ¿En qué estamos gastando el dinero? | Model Studio, vistas de Sankey |
| **3. Optimización** | | Reducir y optimizar los costes | ¿En qué podemos ahorrar? | Métricas calculadas, devoluciones, análisis detallado |
| **4. Valor** | | Alinear las tecnologías de la información con el valor empresarial | ¿Qué valor aporta la tecnología de la información? | Plataforma completa + integraciones de API |

Consejo: La mayoría de las organizaciones operan en el nivel 2 o 3. No hay necesidad de apresurarse a pasar al nivel 4. Cada nivel se basa en el anterior, y avanzar demasiado rápido puede minar la confianza en tus datos de costes. Céntrate en dominar tu nivel actual antes de pasar al siguiente.
