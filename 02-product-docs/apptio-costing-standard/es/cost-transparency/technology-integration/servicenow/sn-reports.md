---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "ServiceNow Informes"
breadcrumb:
  - "Costing Standard"
  - "Integraciones tecnológicas"
  - "ServiceNow"
source_path: "cost-transparency/technology-integration/servicenow/sn-reports.html"
images:
  - "resources/images/ct_images/snr1.jpg"
  - "resources/images/ct_images/snr2.jpg"
  - "resources/images/ct_images/snrep-1.jpg"
  - "resources/images/ct_images/snrep-2.jpg"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# ServiceNow Informes

Aunque actualmente no existen informes específicos ServiceNow en IBM Apptio Costing, la integración (concretamente, la introducción automatizada de conjuntos de datos clave ServiceNow ) mejora significativamente los informes y capacidades existentes IBM Apptio. Producción de inteligencia financiera basada en datos, defendible y de primera clase.

IBM Apptio Las colecciones de informes de costes más afectadas son:

- Servicios
- Aplicaciones
- Productos
- Infraestructura
- Entradas/Mostrador de atención al cliente
- Proyectos

En el lado de ServiceNow, IBM Apptio Egress transfiere el coste total de propiedad (TCO) de aplicaciones y servicios de IBM Apptio a paneles nativos de ServiceNow.

**IBM Apptio Coste total de propiedad del servicio en ServiceNow Gestión de cartera digital (DPM)**

IBM El TCO de los servicios de Apptio aparece de forma nativa en ServiceNow DPM, lo que proporciona a los propietarios de productos y servicios digitales una visibilidad completa de los costes en todas las actividades de planificación, creación y ejecución. Al combinar los datos operativos de la CMDB con el modelo financiero de Apptio, los usuarios obtienen información sobre los principales factores que influyen en los costes, las averías y las tendencias de cada servicio. Esto permite establecer prioridades con mayor conocimiento de causa, mejorar la elaboración de presupuestos y previsiones, y lograr una comprensión unificada del rendimiento financiero de la cartera digital.

El informe proporciona (de arriba abajo):

- Una puerta de acceso a IBM Apptio para obtener un análisis más detallado del informe (la página de destino IBM Apptio se puede configurar en las respectivas propiedades ServiceNow )
- Métricas clave como el coste total de propiedad (TCO) mensual y acumulado en lo que va de año
- Análisis de tendencias de costes en 6months

  ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/snrep-1.jpg)
- Análisis de los principales factores de coste (2 vistas), con los desgloses que usted elija, según el modelo de costes de IBMApptio
- Visibilidad de las 5 principales ofertas de servicios en términos de cambio mensual e impacto

  ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/snrep-2.jpg)

**IBM Apptio Coste total de propiedad (TCO) de la aplicación en una arquitectura empresal (EA) de ServiceNow**

La integración incorpora el TCO de las aplicaciones de IBM Apptio directamente en ServiceNow EA, lo que permite a los arquitectos empresariales evaluar las aplicaciones utilizando tanto el contexto arquitectónico como el impacto financiero. Las decisiones de racionalización de aplicaciones —como invertir, mantener, migrar o retirar— ahora se basan en datos fiables sobre el coste total de propiedad, los factores que influyen en los costes y la alineación con los objetivos de inversión. Esto proporciona a los equipos de EA una fuente única y coherente de información financiera fiable para priorizar la modernización, eliminar redundancias y optimizar la cartera de aplicaciones.

Dos informes destacan las cifras del coste total de propiedad (TCO) de la aplicación de IBM Apptio.

**Informe 1:** Pestaña dedicada al TCO de la cartera en el panel de control de la arquitectura empresarial. Esta pestaña ofrece:

- Total de vistas de TCO de la aplicación a lo largo del tiempo
- El TCO de la aplicación gira en torno a dimensiones críticas como la categoría de la aplicación y la disposición prevista (invertir, mantener, migrar, retirar)
- El TCO de la aplicación como parte del TCO calculado de la aplicación « ServiceNow ». Esta puntuación ayuda a comprender la distribución/ponderación relativa de las distintas aplicaciones. E.g.: ¿Tenemos muchas aplicaciones de bajo o alto coste?
- TCO de la aplicación presentado en 2 ejes:
  - Una de ellas es la disposición planificada (invertir, mantener, migrar, retirar)
  - El otro es un desglose, según su elección y obtenido del modelo de costes de IBM Apptio. Esto podría ser, por ejemplo, un grupo de costes ( g.: ) o una torre de recursos (Resource Tower).

Esta vista ayuda a identificar rápidamente qué áreas tienen un coste significativo asociado. E.g.: Para las aplicaciones marcadas como «Retirar», la mayor parte de los costes se encuentra en la torre de recursos «Compute»

![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/snr1.jpg)

**Informe 2:** Dimensión TCO disponible en el panel de control de racionalización de aplicaciones

El panel de control de racionalización de aplicaciones es un panel de control listo para usar de ServiceNow que le permite comprender rápidamente su panorama de aplicaciones. Presenta las aplicaciones en 4 cuadrantes, impulsadas por la disposición planificada (invertir, mantener, migrar, retirar).

La ubicación de las aplicaciones dentro de estos cuadrantes la define el usuario, basándose en un conjunto seleccionable de medidas principalmente cualitativas, como el valor empresarial, la adecuación técnica y la puntuación de riesgo técnico. El coste total de propiedad (TCO) de la aplicación se puede seleccionar como métrica de dimensionamiento, determinando el tamaño relativo de cada burbuja de aplicación.

![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/snr2.jpg)
