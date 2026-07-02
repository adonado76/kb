---
source_system: "apptio-costing-essentials"
practice: "tbm"
language: "es"
doc_type: "apptio-cost-management"
title: "Conceptos y terminología clave"
breadcrumb:
  - "Costing Essentials"
  - "cómo empezar"
source_path: "apptio-cost-management/getting_started/acm-glossary.html"
images: []
capability_ids: []
last_updated: "2026-02-27"
summary: ""
---
# Conceptos y terminología clave

| Campos | Descripción |
| --- | --- |
| Asignación Ponderación | Porcentaje de gastos en el objeto de origen que se asigna a los objetos de destino  Tal vez una asignación del 100% (insertar "1"), o repartida entre varios tipos/categorías de soluciones |
| Cuenta | Cuenta del libro mayor que se utiliza para recoger y almacenar importes. Cuenta es el código de identificación utilizado en el Libro Mayor. |
| Descripción de cuenta | El nombre de la cuenta del libro mayor. |
| Grupo de cuentas | Agrupación jerárquica de primer nivel de las cuentas del libro mayor Clasificación/agrupación de cuentas que se utilizará en la elaboración de informes. Debe añadirse manualmente a la PTI para que se rellenen los informes CT |
| Subgrupo de cuentas | Agrupación jerárquica de segundo nivel de las cuentas del libro mayor. De fábrica, Apptio admite tres niveles: Grupo de cuentas, Subgrupo de cuentas, Cuenta |
| Métodos de asignación | El método de asignación incluye  Asignación directa  Para la asignación entre una Fuente y un objetivo  La ponderación debe ser 1 por defecto y sólo debe tener una fila.  Porcentaje  Para las asignaciones basadas en porcentajes ponderados  debe tener 2 o más filas con ponderación relativa asignada.  División por volumen  Para asignaciones basadas en atributos de volumen/cantidad (por ejemplo, recuento de licencias de aplicación)  Debe tener 2 o más filas con volúmenes asignados.  Uso estimado ponderado  habilita las columnas % de utilización de efectivos y ponderación de usuarios  debe tener 2 o más filas. |
| ID de transacción AP | Un identificador único para una partida individual en el conjunto de datos de Cuentas a Pagar. |
| Descripción de la transacción AP | La descripción de esta entrada de línea de ID de cuentas a pagar. |
| Relleno | ¿Se trata de sustituir a un empleado o contratista existente? |
| Relaciones comerciales  Director | El principal gestor de cuentas de TI responsable de una unidad de negocio específica. |
| Unidad de negocio | Elemento o segmento lógico de una empresa (como contabilidad, producción, marketing) que representa una función empresarial específica, y un lugar definido en el organigrama, bajo el dominio de un directivo.  En la definición de Apptio, la Unidad de Negocio es el Nivel 1 en la jerarquía de la organización y el Departamento es el Nivel 2 en la jerarquía de la organización. |
| Tipo de unidad de negocio | Una categorización de si la BU (o departamento) genera ingresos o no.  Apptio Los valores recomendados son: "Generador de ingresos", "No generador de ingresos". |
| Compensación | La remuneración total del trabajador.  Por ejemplo: Puede incluir la jubilación y las primas además del salario base |
| Importe del contrato | El importe acordado que se pagará por los servicios prestados en el contrato. |
| Descripción del contrato | Breve descripción del contrato. |
| Días de notificación del contrato | El plazo (en días) en que debe notificarse a un proveedor la no renovación de un contrato o las solicitudes de cambio. |
| Renovación automática del contrato | Indica si un contrato se renueva automáticamente. |
| Número de contrato | El número asignado al contrato por la empresa. |
| Propietario del contrato | El nombre de la persona responsable del contrato. |
| Planes de renovación de contratos | Designa el plan para el futuro del contrato. Valores válidos: Oferta competitiva, Prorrogar como está, Trasladar a la empresa, Trasladar a otro proveedor, Ya no es necesario, Renegociar las condiciones |
| Título del contrato | El título del contrato. |
| Duración del contrato | La duración en días entre la fecha de inicio y fin del contrato. |
| Centro de coste/Código de centro de coste | Un centro de costes es el departamento o "subunidad" de una empresa responsable de sus costes. Centro de coste es el código de identificación utilizado en el libro mayor y los libros auxiliares.  El centro de coste se refiere tanto al departamento que incurrió en el gasto original (por ejemplo, el centro de coste de TI) como a aquellos a los que se cobrarán los servicios de TI del consumidor (centro de coste empresarial) |
| Nombre del centro de costes | Nombre del Centro de Coste asociado al código del Centro de Coste. |
| Pool de costes y subpool de costes | ATUM proporciona una taxonomía estándar del sector para clasificar los gastos, que permite identificar fácilmente su finalidad y facilita el análisis comparativo con los valores de referencia del sector.  Consulte el marco y la taxonomía de TBM y la hoja de taxonomía de grupos de costes en la hoja de cálculo ATUM V4.0 para obtener una definición completa de los grupos y subgrupos de costes de ATUM |
| Importe de la amortización | La cantidad que el activo se deprecia cada periodo. |
| Entrega | Origen de la oferta de servicios/soluciones del proveedor; normalmente: "On Prem"; "Private Cloud", o "Public Cloud" |
| Tipo de empleado | Clasifica los recursos laborales como  **Internos** : Recursos asalariados considerados parte de los PDI Efectivos/ETC  **Externos** : Aumento de personal, incluidos contratistas individuales (propietarios) y empresas de contratación |
| Tipo de gasto | Designa un gasto como OpEx o Capex |
| ID del libro de activos fijos | Un identificador único definido por el usuario para el Libro de Inmovilizado |
| Número de activo fijo | El número de activo o ID del activo |
| Órgano de Gobierno | El Órgano de Gobierno Propietario representa una estructura organizativa de nivel superior a la Unidad de Negocio. Puede utilizarse para distinguir entre diferentes entidades operativas o quizás diferentes estructuras internacionales dentro de la empresa. |
| Objetivo de inversión | estrategia de inversión prospectiva para la aplicación/servicio Utilizada para priorizar los recursos y las inversiones en aplicaciones/servicios nuevos y existentes que están alineados con  imperativos y objetivos de la empresa. |
| ¿Es CSP | (¿Es un proveedor de servicios en nube?)  Designa al proveedor que proporciona servicios en la nube IaaS o PaaS (por ejemplo, computación en la nube, almacenamiento en la nube) al IDP  Los principales proveedores de CSP compatibles con OOTB son Amazon/ AWS, Microsoft/ Azure, Google /GCP, Oracle /OCI  ACM puede incorporar automáticamente los datos de facturación de los proveedores de CSP, asignar y asignar automáticamente los recursos facturados a las ofertas de servicios en ACM |
| Identificación de la revista | El código de identificación del diario para la transacción o el asiento. El asiento contiene la fecha, el nombre de la cuenta y el importe que debe cargarse o abonarse en el Libro Mayor. |
| Identificación laboral | Un identificador único definido por el usuario para el conjunto de datos Laborales |
| Papel laboral | La función principal de los empleados dentro de la organización tecnológica. |
| Etapa del ciclo de vida | El estado actual de la Aplicación/Servicio de Negocio.  Apptio los valores recomendados son: En desarrollo, En servicio, Retirado. |
| ID de la organización | Identificador único para cada consumidor (unidad de negocio)  Selección a partir de una lista de consumidores, introducida en ACM desde la fuente de datos maestros de organización de IDP y enriquecida en ACM mediante el workbench de mapeo de organizaciones |
| Contrato de los padres | El contrato principal del contrato actual utilizado para acumular los gastos de los contratos de mayor envergadura con subcontratos. |
| Número de OC | Un número que identifica una orden de compra asociada con esta entrada de línea de Cuentas por Pagar. |
| Tarifa PO | El tipo de pedido para la función de contratista externo. |
| Proyecto Presupuesto aprobado | Importe de los gastos de capital y de funcionamiento aprobados para un proyecto específico. Esta cifra refleja el último presupuesto total del proyecto aprobado para el año y puede diferir del presupuesto original / base del proyecto. |
| Proyecto Iniciativa Empresarial | La iniciativa empresarial específica definida por la empresa a la que se ajusta el proyecto. Se utiliza para determinar el número de proyectos e inversiones en TI que se están realizando en relación con las distintas iniciativas empresariales, a fin de determinar si las inversiones se ajustan a la estrategia y las iniciativas clave de la empresa. |
| Patrocinador empresarial del proyecto | El empresario principal que patrocina o solicita el proyecto específico. |
| Unidad promotora del proyecto | El nombre de la unidad de negocio que es el patrocinador principal del proyecto. Puede ser de TI o de LOB en función del tipo de proyecto (por ejemplo, proyecto de infraestructura frente a proyecto de LOB). |
| ID de proyecto | Proyecto o inversión Identificador único definido por la cartera de proyectos o el sistema de gestión de inversiones.    Selección a partir de la lista de proyectos, introducida en ACM desde el sistema de registro de gestión de la cartera de proyectos (PPM) de IDP y enriquecida en ACM mediante el banco de trabajo de asignación de proyectos |
| Jefes de proyecto | El principal gestor de proyectos responsable de la planificación y ejecución del proyecto desde la perspectiva de un discípulo de gestión de proyectos. |
| Nombre de proyecto | Nombre único del proyecto o inversión. |
| Número de pedido | El número que identifica una orden de compra asociada con esta entrada de línea de Cuentas por Pagar. |
| Programa del proyecto | Programa se refiere a un grupo de proyectos o inversiones relacionados. |
| Cartera de proyectos | La agrupación de inversiones relacionadas en una "cartera". Se refiere a  la cartera específica a la que pertenece el proyecto o la inversión. |
| Tipo de gasto del proyecto | La categorización de la inversión del gasto o presupuesto en TI. Los valores válidos suelen ser Ejecutar/Modificar la empresa (RTB, CTB)o Ejecutar/Crecer/Transformar la empresa (RTB, GTB, TTB). |
| Motivo previsto | La razón de la plantilla abierta. |
| Número de solicitud | El número de solicitud para el puesto de plantilla aprobado. |
| Banda salarial | La banda salarial utilizada para la imputación ponderada de costes en el modelo de costes. |
| ID de oferta de solución | Identificador único del nombre de la Oferta.    Seleccionar a partir de los valores del Catálogo de Servicios de IDP introducidos en ACM y enriquecidos en ACM a través del Workbench de Mapeo de Soluciones |
| Categoría de la solución | Metadatos que categorizan y organizan las Ofertas de Servicios dentro de su Catálogo de Servicios  Nivel uno de la taxonomía de capas de la solución TBM.  Seleccionar a partir de los valores del Catálogo de Servicios de IDP introducidos en ACM y enriquecidos en ACM a través del Workbench de Mapeo de Soluciones |
| Propietario de TI de soluciones | El principal responsable informático del desarrollo y soporte de la oferta específica. |
| Tipo de oferta de soluciones | Identifica si la oferta se denomina aplicación, producto o servicio en función del modelo operativo de TI. |
| Tipo de solución | Metadatos que categorizan y organizan las Ofertas de Servicios dentro de su Catálogo de Servicios  Segundo nivel de la taxonomía de capas de la solución TBM.  Seleccionar a partir de los valores del Catálogo de Servicios de IDP introducidos en ACM y enriquecidos en ACM a través del Workbench de Mapeo de Soluciones |
| Interacción con el usuario | Categorización del consumidor primario del producto y servicio en relación con la entrega directa y la interacción con el vendedor. Los valores recomendados son: Business Facing (por ejemplo, usuarios empresariales dentro de la empresa), Customer Facing (por ejemplo, los clientes de la empresa), Internal Facing (por ejemplo, internos dentro del departamento de TI)  organización) |
| Categoría de proveedor | Una categorización de alto nivel de la función que ofrece el proveedor.  Puede permitir un análisis más completo de los gastos de los proveedores. Por ejemplo: Comparar gastos de proveedores de la misma categoría |
| ID de proveedor | El sistema de identificación del proveedor utilizado para rastrear la empresa que suministra el producto o servicio    Identificador único para cada proveedor  Seleccionados a partir de una lista de proveedores, introducidos en ACM desde el sistema de registro de proveedores de IDP y enriquecidos en ACM mediante el banco de trabajo de asignación de proveedores  La lista de proveedores no incluye a todos los proveedores, sino a aquellos que representan la mayor parte de su gasto anual (por ejemplo, el 80%).  La lista de proveedores no incluirá a los proveedores que presten servicios de aumento de personal, ya que estos gastos se consideran  (Externos) Gastos de mano de obra |
| Gestor de proveedores | Nombre del principal responsable de la gestión de la relación con el proveedor. Puede ser un responsable formal de compras/proveedor o el responsable de TI que ha contratado los productos o servicios del proveedor. |
| Proveedor Servicio principal | Clasificación del tipo principal de producto o servicio que ofrece el vendedor.    Puede permitir un análisis más completo de los gastos de los proveedores. Por ejemplo: Comparar los gastos de proveedores que prestan los mismos servicios o desempeñan la misma función |
| Tipo de proveedor | Una clasificación de los proveedores que permita una gestión y supervisión adecuadas para optimizar los precios y los riesgos. Las categorías recomendadas son: Estratégico, Preferente y Transaccional    Las categorías recomendadas son: Estratégica, Preferente, Transaccional y Legado. |
| Ponderación | Consulte Ponderación de la asignación |
