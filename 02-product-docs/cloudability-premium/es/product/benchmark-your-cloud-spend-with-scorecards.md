---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Cuadro de mando en Cloudability"
breadcrumb:
  - "Cloudability Premium"
  - "Detalles"
source_path: "product/benchmark-your-cloud-spend-with-scorecards.html"
images:
  - "images/scorecards_1.jpg"
  - "images/scorecards_2.jpg"
  - "images/scorecards_3.jpg"
  - "images/scorecards_4.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Cuadro de mando en Cloudability

Los cuadros de mando le ayudan a comprender lo bien que está gestionando su nube comparando su uso con el de sus homólogos. Los pares son empresas que utilizan los recursos de la nube de forma similar a la suya. Además, Scorecards facilita la comparación entre las distintas unidades de negocio de su organización para que pueda identificar a los equipos que lideran la adopción de prácticas nativas de la nube.

Métricas de puntuación

Hemos identificado tres componentes de una nube bien diseñada que los usuarios finales pueden implantar fácilmente. Todos ellos se puntúan en una escala de 0 a 100, en la que los valores más altos indican una optimización cada vez mayor:

Puntuación de la adecuación : mide la adecuación del tamaño de un recurso a la carga de trabajo. Tenga en cuenta que esto excluye los recursos puntuales, donde no hay necesariamente ninguna penalización por exceso de provisión.

Puntuación de elasticidad : mide la capacidad de activar y desactivar recursos en respuesta a los cambios de la demanda.

Puntuación de precios - Mide lo bien que está aprovechando las diferentes opciones de compra para pagar el mejor precio posible por un recurso determinado.

Puntuación de etiquetado - Mide lo bien que sus equipos están etiquetando sus recursos en la nube.

La puntuación global combina estos tres componentes para ofrecerle una única métrica que mide la eficiencia global de su nube.

![captura de pantalla de scorecards](../../../../03-media/cloudability-premium/images/scorecards_1.jpg)

El primer paso consiste en identificar la dimensión de agrupación y la línea temporal. La dimensión de agrupación es la que utilizará para comparar las distintas unidades de negocio de su empresa. Los cuadros de mando proporcionan métricas de evaluación comparativa basadas en los últimos 10 o 30 días.

![cuadros de mando agrupación de dimensiones captura de pantalla](../../../../03-media/cloudability-premium/images/scorecards_2.jpg)

La visualización de cohortes le ofrece un rápido triaje para identificar los equipos que son baratos y están menos optimizados (abajo a la izquierda) frente a los equipos que son relativamente más caros y están más optimizados (arriba a la derecha).

![Captura de pantalla de visualización de cohortes de tarjetas de puntuación](../../../../03-media/cloudability-premium/images/scorecards_3.jpg)

Uno de los retos que plantea la optimización de la arquitectura de la nube es la disminución de los rendimientos marginales de la optimización. La resolución de los casos más atroces de tamaño medio suele ahorrar a nuestros clientes un 20% de su factura total, pero si llega un punto en el que está mirando una caja individual de m4.xlarge y debatiendo entre pasarse a t3 o a m5a, es posible que haya alcanzado (o cruzado hace tiempo) el punto de rendimiento decreciente.

Mostramos cómo se compara su uso de la nube con la distribución de otras organizaciones que utilizan la nube de forma similar. Basamos estas cohortes de otras organizaciones en diversos factores, como el gasto mensual, los servicios utilizados, el crecimiento histórico de determinados servicios, etc.

![tarjetas de puntuación, captura de pantalla del almacenamiento c,oiud](../../../../03-media/cloudability-premium/images/scorecards_4.jpg)

Preguntas más frecuentes

¿Qué dimensiones puedo utilizar para agrupar unidades de negocio?

Los cuadros de mando admiten etiquetas, asignaciones empresariales, grupos de cuentas e ID de cuentas.

¿Qué recursos en la nube admite Scorecards?

Actualmente ofrecemos compatibilidad con AWS EC2, Azure Compute y GCP Compute Engine. En el futuro añadiremos compatibilidad con otros recursos en la nube.

¿Qué pasa si no utilizo determinadas funciones, como la Redimensión?

Los datos de los que no dispongamos no afectarán a su puntuación. Por ejemplo, si no ha proporcionado credenciales para recopilar métricas de utilización, las puntuaciones de Rightsizing y Elasticity aparecerán como N/A y no se tendrán en cuenta durante la puntuación.
