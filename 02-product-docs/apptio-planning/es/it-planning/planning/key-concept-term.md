---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Conceptos clave y terminología"
breadcrumb:
  - "Planning"
  - "cómo empezar"
source_path: "it-planning/planning/key-concept-term.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Conceptos clave y terminología

Comprender los conceptos básicos de Apptio Planning le ayudará a navegar por la aplicación. A continuación encontrará definiciones de términos clave utilizados frecuentemente en Planificación.

**Objeto de coste (Departamentos)**

Un **objeto de coste es** una estructura financiera utilizada en Apptio Planning para organizar e imputar costes. Proporciona la base para la asignación de gastos, el establecimiento de la propiedad de los costes y el seguimiento del rendimiento financiero.

En Apptio Planning, los Objetos de Coste son sinónimos de **Departamentos** y pueden estructurarse en una **jerarquía**, permitiendo que los costes se desplieguen desde los departamentos de nivel de hoja hasta los grupos de nivel superior. Esta jerarquía permite a las organizaciones ver y analizar los costes a múltiples niveles de detalle, desde los departamentos individuales hasta los roll-ups consolidados.

**[Plan](create-plan.html)**

Un **Plan** es un modelo financiero estructurado en Apptio Planning donde los usuarios introducen, ajustan y analizan datos en un horizonte temporal definido. Los planes pueden representar presupuestos, previsiones o perspectivas plurianuales.

**Plan presupuestario**

Un **Plan Presupuestario** es un tipo de plan que no incluye datos reales. Todos los periodos son totalmente editables, lo que permite a los planificadores establecer proyecciones desde cero o reajustar las expectativas sin verse limitados por los resultados históricos.

**Plan de previsiones**

Un **plan de previsiones** incluye datos reales de periodos históricos. Sólo se pueden editar los periodos futuros, lo que permite a los planificadores ajustar las proyecciones en función de los resultados pasados, manteniendo fijos los resultados reales.

**[Instantánea](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=workflows-submit-review-approve-return-plans#subrevappret__snapshot__title__1 "(se abre en una pestaña o una ventana nueva)") (versión)**

**Las instantáneas** son versiones guardadas del plan de un Departamento que capturan sus datos en un momento determinado. Proporcionan un registro histórico de cómo era el plan de un Departamento cuando se presentó o se guardó manualmente.

- Las instantáneas sólo pueden crearse para **Departamentos de hoja** (el nivel más bajo en la jerarquía de departamentos).
- Cada vez que un Departamento presenta su plan se genera automáticamente una instantánea.
- Los usuarios también pueden crear instantáneas a petición para conservar el estado del plan de un Departamento en cualquier momento.
- Al comparar planes, puede seleccionar una instantánea anterior para comparar, lo que facilita el seguimiento de los cambios, la validación de supuestos y la medición del progreso con respecto a versiones anteriores.

**[Objetivos](set-financial-targets.html "Puede establecer objetivos financieros en Apptio Planning para definir objetivos o límites de gasto para OpEx, CapEx, y Headcount a nivel de departamento. Los objetivos establecen expectativas financieras descendentes que pueden compararse con los datos ascendentes del plan a lo largo de los ciclos de planificación y previsión.")**

**Los objetivos** representan metas financieras o de personal establecidas por los administradores o la dirección. Éstos sirven de referencia para comparar los valores del plan y garantizar la alineación con los objetivos de la organización.

En Apptio Planning, pueden establecerse objetivos para **OpEx**, **CapEx** y **plantilla**, y se aplican a **nivel de departamento**. Estos objetivos orientan a los planificadores y contribuyen a que los planes de los departamentos se ajusten a los objetivos generales de la organización.

**[Gestión de gastos](spend-management.html "La Gestión de Gastos le permite gestionar los datos reales importando las transacciones mensuales a Apptio Planning. La integración de los datos reales permite alinear los modelos de planificación y previsión con el rendimiento real, lo que mejora la visibilidad, el seguimiento de las desviaciones y la toma de decisiones.")**

**La gestión de gastos** es el proceso de importación y gestión de datos reales (datos financieros históricos) en Apptio Planning. Así se garantiza que los planes se basen en unos resultados financieros precisos y actualizados.

**[Datos de referencia](edit-publish-reference.html)**

**Los Datos de Referencia** proporcionan valores estandarizados -como Departamentos, Centros de Coste o Cuentas- que pueden reutilizarse en todos los planes. Garantiza la coherencia, la precisión y la alineación de todas las actividades de planificación.

Cuando se crea un nuevo plan, éste utiliza automáticamente la última **versión publicada** de los Datos de Referencia. Si los Datos de Referencia se actualizan posteriormente, puede actualizar manualmente un plan para utilizar la versión publicada más reciente.

Importante: La actualización de los Datos de Referencia puede provocar a veces la pérdida de datos. Por ejemplo, si se elimina un Centro de Coste o una Cuenta, también se eliminarán todas las partidas relacionadas en el plan.

Para evitar actualizaciones destructivas, puede ajustar la opción **Desactivar restricciones de actualización de datos de referencia** en el perfil de empresa. Cuando las restricciones están desactivadas, el sistema crea automáticamente una copia del plan antes de aplicar las actualizaciones de los Datos de Referencia, lo que le ofrece una opción alternativa si necesita revertir la situación.

**[Dimensión estándar](manage-reference-data.html)**

Las **dimensiones estándar** son las dimensiones predefinidas y listas para usar que proporciona Apptio Planning. Representan las estructuras financieras y organizativas básicas que suelen ser necesarias para la planificación, como Departamentos, Cuentas, Proveedor y Tarifas laborales. Estas dimensiones están siempre disponibles y no se pueden eliminar.

**[Dimensiones personalizadas](manage-custom-reference.html "Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.")**

Las dimensiones personalizadas son **dimensiones creadas por el usuario** que amplían el modelo de datos estándar. Permiten a las organizaciones captar niveles adicionales de análisis o categorización más allá de la estructura preestablecida.

- Puede crear hasta **40 Dimensiones personalizadas**.
- Se pueden añadir dimensiones personalizadas a los esquemas y hacer referencia a ellas en las partidas para facilitar la elaboración de informes, el filtrado y el análisis adaptados a las necesidades de su empresa.

**Atributos**

Los atributos son **campos adicionales (columnas)** que pueden añadirse a una Dimensión o Esquema. Aportan más detalles descriptivos u operativos sin requerir una nueva dimensión. Por ejemplo:

- En una dimensión **Departamento**, puede añadir atributos como *Propietario de departamento* o *Región*.
- En un esquema de **proyecto**, puede añadir atributos como *Prioridad del proyecto* o *Fuente de financiación*.

Los atributos son especialmente útiles para almacenar metadatos que ayuden a generar informes o filtros pero que no requieran una estructura de dimensiones completa.

**Tipos de atributos admitidos** :

|  |  |
| --- | --- |
| **Tipo** | **Descripción** |
| Serie | Almacena valores de texto como nombres, descripciones o códigos. Admite un máximo de 256 caracteres. |
| Fecha | Captura una fecha concreta del calendario (por ejemplo, la fecha de inicio del contrato o la fecha de contratación). |
| Entero | Almacena números enteros sin decimales (por ejemplo, recuento de personal, número de licencias). |
| Numérico | Almacena valores numéricos, incluidos los decimales, para datos financieros o cuantitativos (por ejemplo, coste, tarifa). |
| Porcentaje | Representa valores numéricos como porcentajes (por ejemplo, tasa de asignación, utilización). |
| Nota | Se utiliza para texto largo o notas, como comentarios o descripciones detalladas. Admite un máximo de 1024 caracteres. |
| Lista | Proporciona un conjunto predefinido de valores seleccionables (por ejemplo, región, tipo de departamento). |
| Usuario | Hace referencia a un usuario dentro de Apptio Planning, permitiendo la asignación de propiedad o responsabilidad. |
| Booleano | Almacena valores de verdadero/falso, utilizados para conmutadores o indicadores binarios (por ejemplo, activo/inactivo, sí/no). |
| Enlace | Almacena URLs en las que se puede hacer clic y que se abren en una nueva pestaña del navegador. Útil para hacer referencia a recursos externos, como tickets de Jira, documentación o paneles de control. |

**[Esquema](manage_schema.html "Los esquemas definen la estructura de los datos en Apptio Planning. Especifican las tablas, campos y relaciones que determinan cómo se almacena, vincula y muestra la información en las pestañas de Gastos, como Trabajo, Contratos, Activos y Finanzas.")**

Un **esquema** define la estructura de los datos en Apptio Planning, incluyendo tablas, campos y relaciones. Regula cómo se almacena, enlaza y muestra la información en las tablas de partidas individuales.

Cuando una dimensión coincide con varios tipos de esquemas (Laboral, Contratos, Activos, Actividad Laboral, Reales y el esquema Financiero), ese campo se desplegará automáticamente y se mostrará en la pestaña Resumen.

**Tipos de partidas**

**Los tipos de partidas** definen el tipo de datos que se planifican, rastrean o notifican en Apptio Planning. Cada tipo corresponde a un módulo o función específicos:

- **Partidas financieras** - Captura los gastos de explotación ( OpEx ) o de capital ( CapEx ); aparecen en las pestañas Resumen y Otros.
- **Partidas de mano de obra** - Representan los costes de personal y mano de obra; se gestionan en la pestaña Mano de obra.
- **Partidas de contrato** - Realice un seguimiento de los acuerdos con proveedores y los costes asociados; se gestionan en la pestaña Contrato.
- **Partidas de activo** - Registra las compras de activos y la depreciación; se gestiona en la pestaña Activo.
- **Partidas de actividad laboral** - Capturan el esfuerzo laboral del proyecto (horas) y los cargos cruzados; se gestionan en la pestaña Actividad laboral.
- **Reales** - Representan transacciones financieras reales; se utilizan en la gestión de gastos y rigen las normas de integración de reales.

**[Reglas de asignación de mano de obra](manage-labor-allocation-rules.html)**

**Las reglas de asignación de mano de obra** definen cómo se distribuyen los costes laborales entre las distintas cuentas financieras. Se utilizan para generar costes de mano de obra en varias cuentas del Libro Mayor, garantizando que el coste total de cada plantilla (incluido el salario, las prestaciones y los gastos generales) se represente con precisión en la planificación y los informes financieros.
