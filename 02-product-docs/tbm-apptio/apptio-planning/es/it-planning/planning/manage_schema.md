---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Esquemas"
breadcrumb:
  - "Planning"
  - "Configuración y administración"
source_path: "it-planning/planning/manage_schema.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Esquemas

Los esquemas definen la estructura de los datos en Apptio Planning. Especifican las tablas, campos y relaciones que determinan cómo se almacena, vincula y muestra la información en las pestañas de Gastos, como Trabajo, Contratos, Activos y Finanzas.

Nota: Para gestionar esquemas se requieren los roles de Administrador o Propietario de Proceso Presupuestario.

Desde la página **Esquemas**, los administradores pueden gestionar:

- **Esquemas de Partidas** - Definir estructuras de datos para las partidas de Finanzas, Reales, Mano de Obra, Contratos, Activos y Actividad Laboral.
- Dimensiones **estándar** : dimensiones estándar como **Departamento**, **Cuenta** o **Centro de costes** que se utilizan en todos los esquemas de partidas =
- Dimensiones **personalizadas** : dimensiones creadas por el usuario (hasta 40 para la versión 5.12 ) para datos específicos de la organización.

Los esquemas garantizan la coherencia entre las dimensiones y las partidas, lo que permite a los usuarios analizar los datos sin problemas en todos los planes.

## Gestión de esquemas de partidas

Apptio La planificación admite varios tipos de esquemas, cada uno de los cuales corresponde a un área de planificación clave:

|  |  |
| --- | --- |
| **Tipo de partida** | **Descripción** |
| Finanzas | Captura los gastos operativos y de capital ( OpEx/CapEx ). Los datos de este esquema se muestran en las pestañas **Resumen** y **Otros**. |
| Activos | Realiza un seguimiento de las compras de activos, la depreciación y el impacto financiero a lo largo del tiempo. Los datos de este esquema se muestran en la pestaña **Activos**. |
| Contratos | Se utiliza para gestionar los acuerdos con los proveedores y aplicar planes de amortización. Los datos de este esquema se muestran en la pestaña **Contratos**. |
| Trabajo | Define los efectivos, la remuneración y las normas de asignación para la planificación de los costes laborales. Los datos de este esquema se muestran en la pestaña **Trabajo**. |
| Actividad laboral | Se utiliza para el seguimiento de las horas de mano de obra del proyecto y los cargos cruzados. Los datos de este esquema se muestran en la pestaña **Actividad Laboral**. |
| Actual | Almacena datos transaccionales reales para previsiones y análisis de desviaciones. Los datos de este esquema se muestran en **la Gestión de gastos**. |

## Dimensiones estándar y personalizadas

**Las dimensiones** son datos de referencia compartidos que se utilizan para categorizar y agrupar la información en los distintos esquemas.

Apptio La planificación admite dos tipos:

- **Dimensiones estándar** : se suministran de fábrica, como **Departamento**, **Cuenta** y **Centro de costes**. Se vinculan automáticamente a los esquemas relacionados.
- Dimensiones **personalizadas** : dimensiones creadas por el usuario que le permiten ampliar el modelo de datos para adaptarlo a sus necesidades empresariales. Puede añadir **hasta 40 dimensiones personalizadas para el comunicado 5.12**

Cada dimensión puede incluir **atributos** (columnas) que añaden contexto y detalle, como "Región", "Director" o "Unidad de negocio" Estos atributos están disponibles para filtrar, agrupar y elaborar informes.

Nota: Cuando una dimensión se comparte entre varios tipos de esquema (por ejemplo, “Número de pedido” aparece tanto en Contratos como en Finanzas), los datos de esos esquemas se transfieren automáticamente de la **pestaña Contratos** a la **pestaña Resumen**.

Crear una cota personalizada

1. Vaya a **Planificación** > **Configuración** > **Esquema.**
2. Seleccione la pestaña **Dimensiones personalizadas**.
3. Haga clic en el botón **+** (Añadir).
4. Rellene los siguientes campos:
   - **Nombre** - Introduzca un nombre para la nueva dimensión.
   - **Descripción** - Describa brevemente el propósito de la dimensión.
   - **Añadir a** : seleccione los esquemas de partidas individuales en los que debe estar disponible esta dimensión.
5. Haga clic en **Añadir** para crear la dimensión personalizada.

Editar o eliminar una cota personalizada

Para **editar** :

1. Vaya a **Planificación > Configuración > Esquema**.
2. Seleccione la pestaña **Dimensiones personalizadas**.
3. Haga clic en el nombre de la dimensión o haga clic con el botón derecho → **Editar**.
4. Actualiza los atributos disponibles.

Para **borrar** :

1. Haga clic con el botón derecho en el nombre de la dimensión.
2. Seleccione **Borrar**.

Importante: Al borrar un atributo se eliminan permanentemente todos los datos almacenados en ese campo en todos los planes.

## Atributos personalizados

Los atributos personalizados le permiten ampliar las dimensiones incorporadas o personalizadas con campos adicionales para capturar metadatos relevantes para su organización.

Por ejemplo, podría añadir:

- **"Programa"** o **"Código PEP** " a una dimensión de **Proyecto**.
- **"Región"** a una dimensión de **Departamento**.
- **"Número de pedido"** a un esquema de **contrato**.

Puede añadir **hasta 60 atributos personalizados por dimensión**, y aparecerán como columnas adicionales en las tablas de datos de referencia relacionadas.

Tipos de atributos admitidos

|  |  |
| --- | --- |
| **Tipo** | **Descripción** |
| Serie | Almacena valores de texto como nombres, descripciones o códigos. Admite un máximo de 255 caracteres. |
| Fecha | Captura una fecha concreta del calendario (por ejemplo, la fecha de inicio del contrato o la fecha de contratación). |
| Entero | Almacena números enteros sin decimales (por ejemplo, recuento de personal, número de licencias). |
| Numérico | Almacena valores numéricos, incluidos los decimales, para datos financieros o cuantitativos (por ejemplo, coste, tarifa). |
| Porcentaje | Representa valores numéricos como porcentajes (por ejemplo, tasa de asignación, utilización). |
| Nota | Se utiliza para texto largo o notas, como comentarios o descripciones detalladas. Admite un máximo de 1024 caracteres. |
| Lista | Proporciona un conjunto predefinido de valores seleccionables (por ejemplo, región, tipo de departamento). |
| Usuario | Hace referencia a un usuario dentro de Apptio Planning, permitiendo la asignación de propiedad o responsabilidad. |
| Booleano | Almacena los valores verdadero/falso, utilizados para los toggles o indicadores binarios (por ejemplo, activo/inactivo, sí/no). |
| Enlace | Almacena las URL en las que se puede hacer clic y que se abren en una nueva pestaña del navegador. Útil para hacer referencia a recursos externos como tickets de Jira, documentación o cuadros de mando. |

Añadir un atributo personalizado

1. Vaya a **Planificación** > **Configuración** > **Esquema**.
2. Seleccione la pestaña adecuada - **Partidas**, **Dimensiones estándar** o **Dimensiones personalizadas** - en función de dónde desee añadir el atributo.
3. Haga clic en el **tipo de partida** o **dimensión** específica para abrir sus detalles.
4. En la página **Atributos disponibles**, haga clic en **Añadir**.
5. Rellene los siguientes campos:
   - **Nombre del campo** - Introduzca un nombre para el nuevo atributo.
   - **Tipo de datos** - Elija entre los tipos de atributos admitidos.
   - **Valor por defecto** - Opcionalmente defina un valor por defecto para el campo.
   - **Obligatorio para la introducción de datos** *(sólo esquemas de partidas individuales)* : exija a los usuarios que completen este campo cuando introduzcan datos.
   - **Datos sensibles** *(sólo esquema de partidas de trabajo)* - Restrinja la visibilidad a los usuarios autorizados (controlados por los **[permisos de objetos de coste](manage-cost-object.html)** ).
   - **Acceso restringido** *(sólo esquemas de partidas)* - Limite los derechos de edición a los administradores o usuarios con el permiso ***EditRestrictedDimensions*** permiso.
6. Haga clic en **Añadir** para guardar el atributo personalizado.

Editar o eliminar un atributo personalizado

Para **editar** :

1. Vaya a **Planificación > Configuración > Esquema**.
2. Seleccione la dimensión o el tipo de partida.
3. Abra el cuadro de diálogo **Atributos disponibles**.
4. Haz clic en el nombre del atributo o haz clic con el botón derecho → **Editar**.
5. Actualice el nombre o el valor por defecto y haga clic en **Guardar**.

Para **borrar** :

1. Haga clic con el botón derecho del ratón en el nombre del atributo.
2. Seleccione **Borrar**.

   Importante: Al borrar un atributo se eliminan permanentemente todos los datos almacenados en ese campo en todos los planes.
