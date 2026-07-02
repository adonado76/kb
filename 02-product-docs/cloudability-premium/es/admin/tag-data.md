---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Organiza tus gastos en la nube"
breadcrumb:
  - "Cloudability Premium"
  - "Configuración"
source_path: "admin/tag-data.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Organiza tus gastos en la nube

Los datos de facturación de la nube nativa son, por naturaleza, muy detallados, específicos de cada proveedor y están optimizados para la medición, no para el análisis empresarial. Para que los costes de la nube resulten significativos para los distintos equipos y perfiles de tu práctica de « FinOps », Cloudability ofrece un conjunto de **funciones de organización** que transforman los datos de facturación sin procesar en vistas del gasto coherentes y alineadas con los objetivos empresariales.

A grandes rasgos, estas características ayudan a responder preguntas como:

- *¿Quién es el responsable de este gasto?*
- *¿Cuál es el coste por equipo, aplicación o unidad de negocio?*
- *¿Cómo garantizamos la coherencia y la gestión del etiquetado en las distintas áreas de la empresa?*
- *¿Cómo podemos mantener la coherencia en la presentación de informes de costes a nivel de equipo, departamento y grupo a medida que evoluciona nuestra jerarquía de información?*
- *¿Cuál es el coste de la nube por unidad de actividad empresarial?*

Cloudability organiza el gasto en la nube mediante tres funciones complementarias:

**[Asignación de etiquetas y marcas](map-tags.html)** : normaliza el etiquetado inconsistente

La asignación de etiquetas y marcas te permite estandarizar varias versiones de la misma etiqueta en una única dimensión coherente. Esto garantiza que las etiquetas lógicamente equivalentes se traten como una sola, incluso cuando difieran en formato o en origen. Por ejemplo, asignar varias claves de etiqueta como «Env», «ENV» y «enviro» a una única dimensión denominada «Environment».

**[Grupos de cuentas](account-groups-spend.html)** : estructuran el gasto según la jerarquía de cuentas en la nube (cuentas vinculadas, proyectos, suscripciones)

Los grupos de cuentas permiten agrupar de forma lógica las cuentas en la nube de distintos proveedores en conjuntos significativos, como entornos o departamentos. Al organizar los gastos a nivel de cuenta, los grupos de cuentas ofrecen una forma estable y fácil de entender para segmentar los costes a un nivel general.

**[Asignaciones empresariales](business-tags.html)** : aplican una lógica empresarial personalizada para asignar y clasificar los costes

Las asignaciones empresariales proporcionan un motor basado en reglas que evalúa los datos de facturación y consumo, y asigna los costes a *las dimensiones empresariales* de acuerdo con la taxonomía de tu organización. Estas correspondencias convierten los metadatos específicos de cada proveedor —como etiquetas, nombres de cuentas, regiones o servicios— en categorías empresariales optimizadas para el análisis y la toma de decisiones. De este modo, se garantiza que cada dólar se clasifique y se asigne correctamente.

Además, **[las asignaciones jerárquicas de negocio](hierarchical-business-mapping.html)** pueden utilizarse para definir y mantener relaciones de tipo «padre-hijo» entre dimensiones de negocio relacionadas, lo que permite la agregación escalable de costes y la elaboración de informes coherentes en todos los niveles de la organización a medida que cambian las estructuras.

**[Métricas empresariales](business-metrics.html)** : aplica cálculos aritméticos personalizados y basados en reglas a los datos de costes y uso de la nube para generar métricas financieras específicas para cada empresa

Las métricas empresariales amplían las métricas de costes estándar de « Cloudability », ya que permiten definir cálculos financieros personalizados que transforman los datos brutos sobre costes y uso de la nube en indicadores relevantes para el negocio. Mediante fórmulas configurables y lógica condicional, Business Metrics permite a los equipos modelar las tasas de reembolso, los costes unitarios, los índices de eficiencia y otros indicadores clave de rendimiento (KPI) específicos de la organización.

- **[Asignación de etiquetas y marcadores](../admin/map-tags.html)**
- **[Grupos de cuentas](../admin/account-groups-spend.html)**
- **[Cartografía empresarial](../admin/business-tags.html)**
- **[Métricas calculadas](../admin/calculated_metrics.html)**
