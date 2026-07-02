---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Mapeo de la plataforma de IA"
breadcrumb:
  - "Costing Standard"
  - "Guía paso a paso de Report NX"
  - "Informes de AI TCO NX"
source_path: "cost-transparency/reports/ai-platform-mapping-nx.html"
images:
  - "resources/images/ct_images/nx-aitcomap.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Mapeo de la plataforma de IA

Este informe relaciona el uso de las plataformas de IA con los centros de coste de la organización, lo que permite realizar un recargo y una asignación presupuestaria precisos al atribuir el uso de los servicios de IA a soluciones, unidades de negocio y usuarios específicos de toda la empresa.

Este informe está destinado a los siguientes perfiles:

- Administradores de IA/ML
- Equipos financieros
- Operaciones de TI
- Equipos de ciencia de datos
- Analistas de asignación de costes

## Elementos clave

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/nx-aitcomap.png)

| Elemento | Descripción |
| --- | --- |
| Navegación por pestañas (1) | Navega entre tres vistas de gestión de datos: el enriquecimiento, para añadir detalles de la plataforma; la asignación, para la distribución de costes; y la normalización, para estandarizar las métricas de los tokens. |
| Opciones de filtro (2) | Hay dos listas que te permiten filtrar el informe por nombre de plataforma y nombre de modelo. |
| Panel de instrucciones (3) | Revisa las directrices sobre la jerarquía de asignaciones para garantizar una distribución coherente de los costes: da prioridad a las asignaciones a nivel de solución, luego a las de unidad de negocio y, por último, a las de usuario. |
| Botones de acción (4) | Estos botones permiten acceder a opciones adicionales, publicar los cambios en el mapa o añadir una fila. |
| Tabla de datos cartográficos (5) | Ver y editar las asignaciones de consumo de IA en todas las plataformas, modelos y entidades de la organización. Cada fila vincula un servicio de IA concreto a su centro de costes, con las cantidades de uso que determinan los cálculos de asignación. |

## Preguntas y respuestas

- ¿Qué plataformas y modelos de IA generan costes que deben asignarse?
- ¿Cómo se debe distribuir el consumo de IA entre las distintas soluciones y unidades de negocio para garantizar un reembolso preciso?
- ¿Qué usuarios utilizan qué modelos de IA?
- ¿Cuál es el volumen de uso para cada combinación de plataforma, modelo y consumidor?
- ¿Qué plataformas de IA carecen de asignaciones a centros de coste y requieren una asignación?
- ¿Qué soluciones utilizan varios modelos o plataformas de IA?
- ¿Cómo se distribuye el uso de la IA entre las distintas unidades de negocio?
- ¿Hay alguna plataforma o modelo que aún no se haya incluido en el mapa y que requiera atención?

## Acciones recomendadas

- Revisa la tabla en busca de datos provisionales o de prueba y sustitúyelos por las asignaciones reales de plataforma a centro de coste.
- Haz clic en «Añadir fila» para crear asignaciones para las plataformas de IA que no tengan asignadas soluciones, unidades de negocio o usuarios.
- Asigna los costes primero a la oferta de soluciones (opción preferida), luego a la unidad de negocio y, por último, al ID de usuario como opciones alternativas.
- Comprueba que los valores de consumo sean correctos, ya que estas métricas determinan la distribución de los costes.
- Utiliza los filtros para consultar plataformas concretas ( OpenAI, Hugging Face ) y asegurarte de que se incluyen todos los modelos.
- Haga clic en «Publicar» para activar sus asignaciones en el sistema de imputación de costes.
- Programa revisiones mensuales para incorporar nuevas plataformas, modelos y usuarios de IA a medida que aumenta su adopción.
