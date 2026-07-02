---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Unidad de negocio: primeros pasos"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso de la solución"
  - "Unidad de negocio"
source_path: "cost-transparency/solution-uc/bu-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Unidad de negocio: primeros pasos

El componente Unidades de negocio permite a las organizaciones comprender cómo se consumen los costes tecnológicos en las distintas unidades de negocio mediante la consolidación de los costes de servicios y aplicaciones en una única vista alineada con el negocio. Proporciona una visibilidad completa del coste total de las aplicaciones y los servicios consumidos por cada unidad de negocio, lo que favorece la transparencia, la rendición de cuentas y la toma de decisiones informadas.

## Instalación de componentes

**CT – Unidades de negocio**

El componente CT-Unidades de negocio instala las estructuras de asignación necesarias para transferir los costes de aplicaciones y servicios a las unidades de negocio. Introduce mecanismos de asignación directos e indirectos que garantizan una visión completa y justificable del consumo de las unidades de negocio.

Utilice este componente cuando desee analizar el gasto total en tecnología por unidad de negocio, comprender los factores que influyen en los costes y respaldar iniciativas de showback o chargeback.

## **Requisitos previos**

Debe instalar los siguientes componentes antes de instalar el componente Asignaciones de unidades de negocio:

- CTF: Fuente de costes
- CTF - Torres de recursos informáticos
- CT Apps: aplicaciones
- Aplicaciones de TC - Servicios

**Fuentes comunes de datos**

Los datos de las unidades de negocio suelen proceder de sistemas jerárquicos organizativos, sistemas de recursos humanos, plataformas de gestión de servicios y aplicaciones de planificación empresarial. Los datos que utilice determinarán el nivel de detalle disponible y los métodos de asignación que puede admitir.

Las fuentes de datos comunes incluyen:

- **Sistemas de RR. HH.:** Datos sobre el número de empleados y contratistas para asignaciones indirectas (Workday, SAP SuccessFactors, Oracle HCM).
- **Plataformas de gestión de servicios:** datos de consumo de servicios y asignaciones de unidades de negocio ( ServiceNow, BMC Remedy).
- **Sistemas de planificación empresarial:** estructura de unidades de negocio, programas y proyectos (Anaplan, Adaptive Insights).
- **Gestión de la cartera de aplicaciones:** relaciones entre aplicaciones y unidades de negocio y métricas de consumo.
- **Jerarquía organizativa:** estructura de las unidades de negocio, propiedad y relaciones jerárquicas a partir de los organigramas de la empresa.

**Conjuntos de datos maestros**

Es posible que tenga que cargar varias tablas y asignarlas a las tablas de datos maestros proporcionadas con el componente. Las dos tablas principales de datos maestros son:

- **Datos maestros de asignación de unidades de negocio**
  - Esta tabla define las unidades de negocio de su organización y contiene los atributos utilizados para la asignación de costes indirectos. Incluye información sobre la jerarquía organizativa, datos sobre el número de empleados para los ratios de asignación y detalles sobre la propiedad de las unidades de negocio.
  - **Asignaciones de servicios Datos maestros directos**
  - Esta tabla define la relación de consumo directo entre los servicios empresariales y las unidades de negocio. Contiene las cantidades de consumo que determinan la asignación de costes directos, junto con los identificadores de servicio y unidad de negocio para la asignación.

**Flujo de asignación**

Después de asignar los datos, los costes deberían fluir a través del modelo de la siguiente manera:

- **Servicios empresariales → Asignaciones de servicios directas**
- **Servicios empresariales → Asignaciones de servicios indirectos**
- **Asignaciones de servicios directas → Asignación a unidades de negocio:** costes directos asignados a las unidades de negocio en función de las cantidades consumidas
- **Asignaciones de servicios indirectos → Asignación a unidades de negocio:** costes indirectos asignados a las unidades de negocio en función de los ratios de personal
- **Proyectos → Asignación a unidades de negocio:** Costes del proyecto asignados directamente a las unidades de negocio asociadas

**Asignaciones directas frente a asignaciones indirectas**

En Apptio, los costes se asignan como **directos** o **indirectos** para garantizar una atribución de costes precisa y justificable. **Las asignaciones directas** se basan en el consumo y asignan costes como mano de obra, software o equipos directamente a un producto, servicio, departamento o proyecto específico. Estos costes pueden asignarse claramente a un objeto de coste y suelen representar la mayor parte del gasto controlable. **Las asignaciones indirectas** representan los costes compartidos o generales necesarios para el funcionamiento de la organización, tales como instalaciones, servicios públicos, equipos para usuarios finales e infraestructura general, y se distribuyen utilizando ratios de asignación definidos, como el número total de empleados o el número de empleados por departamento.

Dentro del modelo de costes « Apptio », las asignaciones directas e indirectas se calculan en la parte superior del modelo utilizando cuatro objetos principales: **Servicios empresariales**, **Asignaciones de servicios directas**, **Asignaciones de servicios indirectas** y **Asignación de unidades de negocio**. Los costes de los servicios empresariales se transfieren a **las asignaciones de servicios directas** basándose en asignaciones explícitas de niveles de servicio, mientras que los costes compartidos se transfieren a **las asignaciones de servicios indirectas** basándose en la lógica de asignación configurada. Esta estructura garantiza una separación clara entre los costes directos derivados del consumo y los costes indirectos compartidos, lo que permite una mayor transparencia, coherencia y precisión en la presentación de informes posteriores en todos los servicios, aplicaciones y unidades de negocio.
