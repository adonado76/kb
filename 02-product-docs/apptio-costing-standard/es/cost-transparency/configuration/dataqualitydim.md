---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Cargar los datos de las Dimensiones de Calidad de Datos"
breadcrumb: []
source_path: "cost-transparency/configuration/dataqualitydim.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Cargar los datos de las Dimensiones de Calidad de Datos

Para rellenar las puntuaciones de validez en el informe de calidad de Data Dimensions, cargue las cuatro tablas de datos: Validez de la fuente de costes, Validez de la mano de obra, Validez de proyectos y Validez de proveedores.

Se aplica a: Costing Standard en TBM Studio 12.0 y posteriores

## Introducción

La validez mide la correspondencia entre los datos de fuentes de costes, mano de obra, proyectos y proveedores y un conjunto de valores aceptados para los datos. Los valores aceptados se almacenan en cuatro tablas de datos maestros dentro de la categoría Dimensiones de la calidad de los datos:

- Coste Fuente Validez
- Validez laboral
- Validez de los proyectos (si se hace un seguimiento de los costes del proyecto)
- Validez del proveedor (si se hace un seguimiento de los costes del proveedor)

Para cada tabla de datos maestros, se carga un único conjunto de datos que se anexa y se asigna al conjunto de datos maestros correspondiente. El conjunto de datos cargado debe contener columnas que puedan asignarse a las columnas apropiadas de la tabla de datos maestros.

## Descripción de la columna Validez de la fuente de costes

Las columnas del conjunto de datos maestros Validez de la fuente de costes se describen en la tabla siguiente. Las columnas se enumeran en el orden en que aparecen en el conjunto de datos. Las columnas obligatorias están marcadas con un asterisco ( \* ). Los valores posibles válidos para una columna distinguen entre mayúsculas y minúsculas.

Las abreviaturas que figuran a continuación se utilizan en la columna Tipo.

- A = Etiqueta
- # = Numérico
- D = Fecha
- ID = Identificador único
- K = Campo clave utilizado en la asignación entre objetos modelo

| Columna | Tipo | Descripción |
| --- | --- | --- |
| Cuenta | A | El nombre o identificador de la cuenta. |
| Centro de costes | A | Departamento u otra unidad de una organización a la que se asignan costes directos o indirectos. |
| Propietario del centro de costes | A | El propietario del centro de coste. |
| Pool de costes | A | Nombre del conjunto de costes. Valores válidos: Hardware, Software, Mano de obra, Servicios externos, Instalaciones Energía, Telecomunicaciones, Otros |
| Sub Pool de costes | A | Una subcategoría de los gastos comunes. Por ejemplo, HW-Maintenance Support es un elemento del subgrupo de costes del grupo de costes Hardware. Valores válidos: Consultoría, Mano de obra externa, Instalaciones y energía, Amortización de HW, Gastos de HW, Arrendamiento de HW, Mantenimiento y soporte de HW, Mano de obra interna, Otros, Proveedores de servicios, Amortización de SW, Gastos de SW, Arrendamiento de SW, Mantenimiento y soporte de SW, Telecomunicaciones. |
| Tipo de gasto | A | El controlador de métricas del modelo de objeto Fuente de costes que se rellena con los datos de esta partida - los valores posibles son: CapEx, OpEx, CapEx Presupuesto y OpEx Presupuesto. |
| Fijo Variable | A | Designa si el coste debe clasificarse como coste fijo o variable. Los valores válidos son: Fijo, Variable. |
| Propietario (Owner) | A | La persona responsable de la partida. |
| Válido | # | Se trata de un campo del sistema. No introduzca ningún valor. |

## Descripciones de las columnas de Validez Laboral

Las columnas del conjunto de datos maestros Validez laboral se describen en la tabla siguiente. Las columnas se enumeran en el orden en que aparecen en el conjunto de datos. Las columnas obligatorias están marcadas con un asterisco ( \* ). Los valores posibles válidos para una columna distinguen entre mayúsculas y minúsculas.

Las abreviaturas que figuran a continuación se utilizan en la columna Tipo.

- A = Etiqueta
- # = Numérico
- D = Fecha
- ID = Identificador único
- K = Campo clave utilizado en la asignación entre objetos modelo

| Columna | Tipo | Descripción |
| --- | --- | --- |
| Tipo de empleado | A | El tipo de recurso laboral, como Personal Externo o Personal Interno. |
| Identificación laboral | A | Identificador único definido por el usuario para el conjunto de datos Laborales. Esta columna no debe tener valores duplicados. |
| Nombre laboral | A | El nombre del recurso laboral, como John Smith. |
| Ubicación | A | La ubicación asociada al recurso laboral. |
| Posición | A | El nombre del puesto del empleado position.For ejemplo: Helpdesk, soporte, administrador de escritorio, administrador de almacenamiento. |
| Región | A | La región geográfica asociada a este recurso laboral. |
| Válido | # | Se trata de un campo del sistema. No introduzca ningún valor. |

## Proyectos Descripción de las columnas de validez

Las columnas del conjunto de datos maestros Validez de los proyectos se describen en la tabla siguiente. Las columnas se enumeran en el orden en que aparecen en el conjunto de datos. Las columnas obligatorias están marcadas con un asterisco ( \* ). Los valores posibles válidos para una columna distinguen entre mayúsculas y minúsculas.

Las abreviaturas que figuran a continuación se utilizan en la columna Tipo.

- A = Etiqueta
- # = Numérico
- D = Fecha
- ID = Identificador único
- K = Campo clave utilizado en la asignación entre objetos modelo

| Columna | Tipo | Descripción |
| --- | --- | --- |
| Iniciativa empresarial | A | Proyectos o programas específicos emprendidos para alcanzar objetivos concretos a corto plazo, como reducir costes, aumentar la eficiencia y mejorar el rendimiento de las ventas. |
| Patrocinador empresarial | A | Persona o entidad que organiza y se compromete con el desarrollo de un producto, programa o proyecto. |
| Propietario de proyecto de TI | A | El propietario del proyecto. |
| ID de proyecto | A | Identificador del proyecto. |
| Gestor de proyectos | A | El contacto principal para este proyecto dentro de la empresa. |
| Nombre de proyecto | A | Un nombre único para el proyecto, como Oracle v9 Migration o Virtualization Deployment. El nombre del proyecto se utiliza en los informes para desglosar los costes. |
| Cartera de proyectos | A | Una categorización de alto nivel del proyecto. Una cartera puede contener uno o varios proyectos. |
| Tipo de gasto | A | La categorización de la inversión del gasto o presupuesto en TI.  Los valores válidos suelen ser: Dirigir la empresa, Cambiar la empresa y Transformar la empresa.  Valores válidos: **RTB**, **CTB** o **TTB** |
| Válido | # | Se trata de un campo del sistema. No introduzca ningún valor. |

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
