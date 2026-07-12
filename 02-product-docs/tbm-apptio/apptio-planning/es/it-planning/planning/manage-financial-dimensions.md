---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Datos de referencia de las Dimensiones Financieras"
breadcrumb: []
source_path: "it-planning/planning/manage-financial-dimensions.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Datos de referencia de las Dimensiones Financieras

Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.

Las dimensiones son las categorías de datos esenciales en las partidas presupuestarias. Muchas dimensiones incorporadas tienen dependencias con otras dimensiones (para más información, véase [Atributo de datos de referencia y dependencias de dimensiones](manage-reference-data.html) ). Puede importar datos de referencia de dimensiones desde un archivo.csv o desde Costing Standard y exportar plantillas de datos de referencia de dimensiones y datos de tablas (véase [Gestionar dimensiones](manage-reference-data.html) ).

![imagen](../../resources/images/it%20planning_images/icon_video.png)

Vea estos vídeos de Apptio Education Services:

- [Configuración de los Datos de Referencia: Dimensiones Financieras y Permisos de Objetos de Coste](https://community.ibm.com/community/user/viewdocument/configuring-reference-data-financi?CommunityKey=4100dfb8-fc23-4203-83c7-019253cf7c0b&tab=librarydocuments "(se abre en una pestaña o una ventana nueva)").
- [Comprender las jerarquías de datos en la planificación](https://community.ibm.com/community/user/viewdocument/understanding-data-hierarchies-in-i?CommunityKey=2e85ed45-9b8a-486c-bd55-019253d466eb&tab=librarydocuments "(se abre en una pestaña o una ventana nueva)").

## Gestionar los datos de referencia de la cuenta

Tras la importación inicial y la configuración de sus cuentas, es importante mantener su archivo.csv de datos de Cuentas, incluida la asignación de grupos de costes para futuras actualizaciones de importación.

En el menú de navegación del Plan Costing & Planning , seleccione **Configuración > Datos de referencia > Cuenta**.

Esta tabla de datos incluye lo siguiente:

- **Código** (obligatorio) - Identificador único de una cuenta del libro mayor, utilizado para importar reales del libro mayor.
- **Nombre** (obligatorio) - Nombre de la cuenta.
- **Código padre** - Representa la jerarquía de su cuenta. Es el valor del código de su cuenta inmediatamente superior o matriz (si existe).
- **Categoría** - Grupos de cuentas del libro mayor utilizados para el análisis de desviaciones. Consulte la siguiente sección "[Gestionar datos de referencia de categoría de cuenta](#FinancialDimensionsreferencedata__ManageAccountCategoryreferencedata) "
- **Pool de costes** - La [categoría ATUM](../../atum/home.html) a la que pertenece la cuenta.
- **Tipo de gasto** (obligatorio) - Define la cuenta del libro mayor como cuenta de explotación ( OpEx ) o de capital ( CapEx ). Si está en blanco, el valor por defecto es OpEx.
- **Grupo** -

Sugerencia:

- No se pueden editar directamente valores distintos a los del pool de costes en la tabla Cuenta. Mantenga los datos de su plan de cuentas en un libro de Excel basado en la plantilla.csv, reimporte y vuelva a publicar el archivo.csv según sea necesario.
- Se recomienda generar nuevos archivos.csv a partir del libro de Excel en lugar de editar directamente el archivo.csv. Trate el libro de Excel como editable y el archivo.csv como de sólo lectura. De lo contrario, Excel puede eliminar los ceros a la izquierda al abrir un archivo.csv, lo que puede crear problemas con los números de cuenta que incluyen ceros a la izquierda.
- También puede personalizar sustancialmente las dimensiones de los datos de referencia y las tablas de elementos de línea (consulte [Administrar datos de referencia personalizados (dimensiones, listas y tablas de elementos de línea).](manage-custom-reference.html "Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.")

## Gestionar los datos de referencia de la categoría de cuenta

Esta dimensión agrupa las cuentas detalladas del libro mayor en una lista manejable para el análisis de desviaciones. Véase [Analizar la desviación presupuestaria](analyze-budget-variance.html "Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor."). se recomiendan de 10 a 15 valores discretos para esta dimensión. Es posible que ya tenga algo similar implementado como atributo personalizado en los datos de referencia de su Cuenta.

Nota: La dimensión Categoría de cuenta no admite actualmente la importación desde Costing Standard. No obstante, puede crear los datos de referencia en Costing Standard (véase [Integración con Transparencia de costes](integrate-ct.html "Si su organización utiliza tanto Apptio Costing Standard como una aplicación de planificación Apptio, puede integrarlas para compartir datos.") ).

1. En el menú de navegación del Plan Costing & Planning  , seleccione Configuración > Datos de referencia > Categoría de cuenta.
2. Actualice los valores de la tabla de datos según sea necesario:
   - Código (obligatorio) - Identificador único de la categoría o agrupación de su cuenta (por ejemplo, ADMIN)
   - Nombre (obligatorio): nombre de la categoría o agrupación de su cuenta (por ejemplo, Instalaciones y Administración)

A continuación se muestran algunos ejemplos de valores de datos de referencia de Categoría de cuenta:

| Código | Nombre |
| --- | --- |
| CAPITAL | Inversiones de capital |
| Consultoría | Consultoría |
| EXT-LABOR | Contratar mano de obra |
| DEPRECIACIÓN | Depreciación |
| ADMIN | Administración de instalaciones y oficinas |
| EMP-OTHER | Otros costes de personal |
| SERVICIOS | Servicios exteriores |
| EMP-SALARIO | Salarios y prestaciones |
| TECH | Tecnología |
| TELECOM | Telecomunicaciones |

## Gestionar los datos de referencia de los centros de costes

Los Centros de Coste representan atributos de partida que se asignan a Objetos de Coste.

1. En el menú de navegación del Plan Costing & Planning  , seleccione Configuración > Datos de referencia > Centro de coste.
2. Actualice los valores de la tabla de datos según sea necesario:
   - Código (obligatorio) - El identificador único del Centro de Coste (normalmente proporcionado por su sistema financiero corporativo), utilizado para importar reales desde el libro mayor y empleado en planes para integrarse con sistemas financieros corporativos.
   - Nombre (obligatorio) - Nombre del centro de costes.
   - Código padre - Representa la jerarquía de su Centro de Coste. Es el valor del código de su Centro de Coste inmediatamente superior o matriz (si existe). Tenga en cuenta que la jerarquía del Centro de Coste no está relacionada con la jerarquía de aprobación del presupuesto o del plan de previsiones en las aplicaciones de Apptio Planning . Éstos vienen determinados por los Permisos para Objetos de Coste de su organización (véanse los datos de referencia de Gestionar Permisos para Objetos de Coste.

## Gestionar los datos de referencia del Departamento

Esta dimensión representa la estructura de su organización. En concreto, los Departamentos representan la estructura jerárquica de su organización de TI (o la estructura que prefiera) para la planificación presupuestaria y la elaboración de informes. Los departamentos son un tipo de objeto de coste (los proyectos son otro ejemplo de objetos de coste). Los datos de referencia de Permisos de objetos de coste determinan quién puede editar cada Departamento y quién puede aprobar presentaciones de planes presupuestarios. Véanse [los datos de referencia de los Permisos para Gestionar Objetos de Coste.](manage-cost-object.html "Los Permisos de Objetos de Coste determinan qué usuarios pueden ver, editar, enviar o aprobar planes a nivel de Departamento (Objetos de Coste). Cada Departamento puede tener uno o más usuarios asignados con permisos de nivel de edición y, para las aprobaciones de varios niveles, permisos de nivel de aprobación.")

Importe y publique datos de referencia para su Departamento utilizando archivos con formato.csv mantenidos fuera de sus aplicaciones Apptio Planning .

1. En el menú de navegación del Plan Costing & Planning  , seleccione Configuración > Datos de referencia > Departamento.
2. Actualice los valores de la tabla de datos según sea necesario:
   - Código (obligatorio) - Identificador único del Departamento.
   - Nombre (obligatorio) - Nombre del Departamento.
   - Código padre - Representa la jerarquía de su Departamento.
   - Código de moneda - La moneda común para el Departamento. Requerido cuando se habilitan múltiples monedas (ver Soporte para múltiples monedas). El valor de la moneda común del Departamento debe ser el código ISO de tres letras de la moneda. Si no se introduce ningún código de moneda, se utilizará la moneda común por defecto. - Grupo de precios - Determina el grupo de precios del departamento para los modelos de precios basados en regiones o por niveles.
   - Código de centro de coste por defecto - El valor por defecto a menos que se proporcione un valor de código de centro de coste diferente.
   - Código de Centro de Coste - El identificador de los Centros de Coste correspondientes (véase Gestionar datos de referencia del contrato). Al importar los reales, se asignan por Centro de Coste, y luego se asignan a Objeto de Coste (véase Importar y publicar reales). Un Departamento puede estar asociado a múltiples Centros de Coste y puede incluir partidas (volúmenes, mano de obra o gastos) registradas para más de un Centro de Coste. Añada múltiples Centros de Coste a la celda de la tabla utilizando una coma para separarlos. NOTA: Un Departamento puede estar asociado a varios Centros de Coste, pero un Centro de Coste sólo puede estar asociado a un Departamento.

**VER TAMBIÉN** : [Actualizar la jerarquía de departamentos](update-department-hierarchy.html)

## Gestionar los datos de referencia de localización

Al definir la Ubicación, puede determinar dónde se incurrirá en los costes. Además, la ubicación ayuda a definir otras dimensiones, como el impuesto sobre el valor añadido (IVA). Véase [Gestionar datos de referencia del contrato](manage-contract-configuration.html "Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.") )

1. En el menú de navegación del Plan Costing & Planning  , seleccione **Configuración > Datos de referencia > Ubicación**.
2. Actualice los valores de la tabla de datos según sea necesario: **Nombre**, **Continente** y **País** de la Localización.

## Gestionar los datos de referencia del controlador de desviaciones

Esta dimensión define una lista configurable de controladores de varianza comunes para sus usuarios. Este enfoque estructurado permite la elaboración de informes continuos sobre los factores de desviación. Véase [Analizar la desviación presupuestaria](analyze-budget-variance.html "Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.").

**NOTA** : (para usuarios de Costing Standard ): Si construye los datos de referencia **de Categoría de Cuenta** en Costing Standard y luego los mapea a Cuenta, la importación desde Costing Standard importará esos mapeos a su aplicación Apptio Planning . Véase [Integrar con transparencia de costes](integrate-ct.html "Si su organización utiliza tanto Apptio Costing Standard como una aplicación de planificación Apptio, puede integrarlas para compartir datos."). Variance Driver no admite actualmente la importación desde Costing Standard.

1. En el menú de navegación del Plan Costing & Planning  , seleccione Configuración > Datos de referencia > Controlador de desviaciones.
2. Actualice los valores de la tabla de datos según sea necesario:
   - Código (obligatorio) - Identificador único de su controlador de varianza (por ejemplo, TIMING)
   - Grupo - Determina el grupo para el controlador de desviaciones (en desarrollo, dejar en blanco)
   - Nombre (obligatorio) - Nombre del controlador de varianza (por ejemplo, Temporización del proyecto)

Ejemplo Varianza Conductores valores de datos de referencia:

| Código | Grupo | Nombre |
| --- | --- | --- |
| Impacto | Contabilidad | Impacto contable |
| TIEMPO | Contabilidad | Calendario contable |
| RUNRATE | Operaciones | Variación de la tasa de ejecución |
| PIVOT | Proyectos | Cambio en la inversión estratégica |
| FOREX | Otros | Impacto de las divisas |
| CRECIMIENTO | Operaciones | Crecimiento |
| SERVICIOS | Operaciones | Calendario de impacto de los servicios gestionados |
| OTROS | Otros | Otros (<20%) |
| PROYECTO | Proyectos | Calendario del proyecto |
| DEMANDA | Operaciones | Variación de la demanda de recursos |
| UNPLANNED | Otros | Gastos imprevistos |

## Gestionar los datos de referencia de los proveedores

Al definir el proveedor, los responsables del presupuesto pueden contabilizar los costes de empresas externas.

1. En el menú de navegación del Plan Costing & Planning  , seleccione **Configuración > Datos de referencia > Proveedor**.
2. Actualice los valores de la tabla de datos según sea necesario: **Nombre** y **Grupo** asociado al proveedor.
