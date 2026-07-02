---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Valores de visualización"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Propiedades de informe"
source_path: "studio/new-uc/reference/report-studio-reference/display-settings.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Valores de visualización

Los ajustes de visualización controlan la presentación visual y el comportamiento de actualización de los informes.

**Actualización diferida**

La actualización diferida controla la rapidez con la que se actualizan los informes cuando los usuarios interactúan con filtros, segmentadores y selectores. Esta configuración ayuda a gestionar el rendimiento de los informes complejos.

|  |  |
| --- | --- |
| **Opción** | **Comportamiento** |
| Retardo de actualización: 3s | El sistema espera 3 segundos tras seleccionar un filtro antes de actualizar el informe. Permite a los usuarios realizar varias selecciones antes de que se actualice la página. Esta es la configuración predeterminada. |
| Renovación manual | El informe no se actualiza hasta que el usuario haga clic explícitamente en «Actualizar». Recomendado para informes extensos con numerosos filtros y selectores en los que cada actualización lleva mucho tiempo. |

**Configuración predeterminada a nivel de proyecto:** ve a la pestaña «Proyecto» > «Configuración del proyecto» > «Actualización diferida» para establecer la configuración predeterminada para todos los informes.

**Modificación a nivel de informe:** extraiga el informe y, a continuación, modifique la configuración de actualización en la pestaña «Informe».

**Paleta de colores**

Los informes pueden utilizar paletas de colores personalizadas para mantener la coherencia de la imagen de marca en todos los gráficos y visualizaciones. Las paletas de colores las definen los administradores a nivel de entorno y pueden aplicarse tanto a la colección de informes como a cada informe individual.

**Jerarquía de la paleta de colores:**

1. La paleta de nivel de informe (si está configurada) tiene prioridad
2. La paleta de recopilación de informes se aplica si no hay ninguna sustitución a nivel de informe
3. Si no se ha configurado ninguna paleta personalizada, se aplicarán los colores predeterminados de Apptio

**Para aplicar una paleta de colores:**

1. Echa un vistazo al informe
2. Ve a la pestaña «Informe» > «Paleta de colores»
3. Elige entre paletas personalizadas u opciones predefinidas

Nota: *Las paletas de colores afectan a la mayoría de los tipos de gráficos, excepto a los gráficos en cascada y a los mapas de árbol. No afectan al formato de las tablas, las fuentes, los segmentadores, los fondos ni los componentes de los KPI.*

**Tema principal:** [Propiedades del informe](../../../../studio/new-uc/reference/report-studio-reference/report-properties.html)
