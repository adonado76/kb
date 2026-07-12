---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Conceptos esenciales de TBM Studio"
breadcrumb: []
source_path: "studio/admin/essential-tbmstudio-concepts.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Conceptos esenciales de TBM Studio

Se aplica a: TBM Studio 12.0 y posteriores. En TBM Studio, usted organiza su trabajo en proyectos. Dentro de un proyecto, se recopilan y transforman datos en conjuntos de datos, se crean modelos, se añaden objetos a los modelos, se asignan conjuntos de datos a los objetos, se imputan costes de un objeto a otro y se resumen los resultados en uno o varios informes. Instancias, dominios y proyectos organizan tu trabajo:

- **Instancia** - Un Apptio SaaS (Software as a Service) que alberga dominios y proyectos de clientes. Dentro de una instancia, puede haber varios dominios. Dentro de un dominio, puede haber varios proyectos.
- **Dominio** - El entorno Apptio establecido para una organización específica. A su organización se le ha asignado un dominio que contiene todos sus proyectos.
- **Proyecto** - El área de cálculo dentro de un dominio Apptio en el que se crean modelos e informes. Un proyecto contiene conjuntos de datos, métricas e informes interrelacionados e interdependientes.

El flujo de trabajo básico para construir un proyecto incluye:

- Crear tablas a partir de datos importados.
- Crear un modelo para mostrar el flujo de datos a través de la organización. El dato más utilizado es el coste. Un modelo calcula el coste de los servicios que ofrece su organización.
- Crear métricas del modelo para calcular diferentes valores. Por ejemplo: coste, presupuesto, previsión.
- Construya el modelo asignando costes de una tabla a otra. Las tablas de origen pueden ser un libro mayor o una factura de servicios web. Las tablas de destino pueden ser aplicaciones y unidades de negocio.
- Definir métricas calculadas a partir de las métricas modeladas y las tablas de datos. Una métrica calculada común resta los costes reales de los costes previstos.
- Crear informes para presentar los datos calculados en los modelos.

Su entorno Apptio contiene uno o varios proyectos que organizan su trabajo de modelización y elaboración de informes. Los proyectos constan de los siguientes elementos:

- **Tablas** de datos - Las tablas de datos contienen los datos de su proyecto. Puede cargar datos de varias fuentes, incluidos archivos de Excel y archivos planos delimitados por comas, tabulaciones, tubos u otros separadores. Entre las fuentes de datos habituales se encuentran un archivo del libro mayor y una factura de servicios web. Para más información, consulte [Acerca de Data Studio](../data_studio/data-transform-chapter-title-page.html "Se aplica a: TBM Studio 12.0 y posteriores").
- **Modelo** de datos - Un modelo de datos es una representación lógica y gráfica de los costes, la utilización, los niveles de servicio u otros datos relevantes para sus servicios de TI. La estructura del modelo de datos de un proyecto determina el tipo de información que puede mostrarse en los informes de ese proyecto. Para más información, consulte [Acerca de Data Studio](../data_studio/data-transform-chapter-title-page.html "Se aplica a: TBM Studio 12.0 y posteriores").
- **Métricas** - Las métricas son cálculos que definen el valor. Existen dos tipos de métricas:
  - **Métricas modeladas** - Un modelo de datos es en sí mismo una métrica. Un modelo calcula una única medida, como el coste o el presupuesto. Los modelos de datos se denominan a veces métricas modeladas.
  - **Métricas** calculadas: una métrica calculada utiliza una fórmula para obtener un valor a partir de métricas modeladas. Por ejemplo, puede crear una métrica calculada denominada Varianza\_presupuesto que reste la métrica del modelo Coste de la métrica del modelo Presupuesto. Para más información, consulte [Crear y gestionar métricas](../model_studio/introduction-to-metrics.html "Se aplica a: TBM Studio 12.0 y posteriores").
- **Informes** - Un modelo de datos correctamente estructurado le permitirá crear una variedad de informes útiles con una granularidad que satisfaga sus requisitos de elaboración de informes. Para obtener más información, consulte [TBM Studio Acerca de Report Studio](../reports/report_studio_title_topic.html).

- **[TBM Studio Acerca de Report Studio](../../studio/reports/report_studio_title_topic.html)**
- **[Diseño del informe](../../studio/reports/report-layout.html)**  
   **Se aplica a** : TBM Studio 12.0 y posteriores
