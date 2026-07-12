---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Integración de la Transparencia de Costes (Legacy)"
breadcrumb:
  - "Planning"
  - "Integraciones"
  - "Conéctese a Apptio Costing"
source_path: "it-planning/planning/integrate-ct.html"
images:
  - "resources/images/icons/icon-settings_20x20.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Integración de la Transparencia de Costes (Legacy)

Si su organización utiliza tanto Apptio Costing Standard como una aplicación Apptio Planning , puede integrarlas para compartir datos.

La integración de Costing Standard con una aplicación Apptio Planning le permite lograr lo siguiente:

- Importe datos de referencia de Costing Standard a su aplicación Apptio Planning
- Importe los datos reales mensuales de Costing Standard a su aplicación Apptio Planning
- Publique planes presupuestarios y previsiones desde su aplicación Apptio Planning en Costing Standard

Para obtener más información, consulte [Solución de errores de carga de datos de planificación](troubleshooting.html)

## Habilitar integración

Las tareas de esta sección sólo pueden ser realizadas por usuarios asignados a la función Admin. Ver permisos y roles de Frontdoor.

Un panel Cost Transparency Integration (CTI) mejorado, introducido en la versión de planificación 2.78, es un espacio autónomo en el que los usuarios administradores pueden realizar todas las tareas de Cost Transparency Integration dentro de un único panel de control. El panel ofrece gestión centralizada e importación y exportación con un solo clic con Costing Standard. Para más información, consulte [Cost Transparency Integration Panel](cti_panel.html "El panel actualizado de Integración de Transparencia de Costes (CTI), introducido en la versión de planificación 2.78, es un espacio autónomo en el que los usuarios administradores pueden realizar todas las tareas de Integración de Transparencia de Costes dentro de un único panel de control. El nuevo panel ofrece gestión centralizada e importación y exportación con un solo clic y Transparencia de costes.").

En Costing Standard, instale el componente Apptio ITPF Integration. Al hacerlo, se instalan automáticamente todas las plantillas de los conjuntos de datos de referencia necesarios para integrar los productos. Si utiliza Activos y Vendedor, deberá instalar también los componentes Apptio ITPF Asset y Apptio ITPF Vendor. Para obtener más información, consulte [Instalar los componentes de integración ITPF](../../cost-transparency/configuration/installitpfintegration.html "Hay tres componentes disponibles como parte del módulo Costing Standard Foundation para conectar Costing Standard (CT) con IT Planning Foundation (ITPF).") en la ayuda de Costing Standard .

Puede integrar Costing Standard utilizando uno de los siguientes métodos de autenticación:

Autenticación por token ( R12+ ) (recomendado)
:   Este método determina la instancia Costing Standard y el dominio del proyecto a partir de la configuración del entorno. El entorno Enhanced Access Administration y el token de autenticación del usuario se incluyen en la solicitud.

    Cualquier usuario con permisos **ManagePlans**, **CTIConfig** y **ReadOnlyApi** (permisos incluidos en la función Admin por defecto) puede autenticarse para publicar planes e importar datos de Costing Standard.

    Si se autentica utilizando **la autenticación Token ( R12+** ), también debe elegir un **Entorno**. Esto le permite utilizar la misma instancia o proyecto de Costing Standard para las instancias de planificación principal y de caja de arena al exportar datos de planificación o importar datos reales y/o de referencia a y desde Costing Standard. Por ejemplo, puede importar información de datos reales y de referencia de la misma instancia o proyecto de Costing Standard tanto al entorno de pruebas de planificación como a las instancias principales o de producción.
:   [Integrar utilizando autenticación Token ( R12+ )](#IntegratewithCostTransparency__Integrat)

Autenticación de la cuenta de servicio
:   La autenticación de cuentas de servicio ya no es compatible con Costing Standard v12.9.0 o posterior.

    Este método determina la instancia Costing Standard y el dominio del proyecto a partir de la configuración introducida por el usuario para ese tipo de integración en particular. Las credenciales de la cuenta de servicio se pasan como una cabecera de autenticación "básica" de HTTP.

    Si su aplicación Costing Standard se ejecuta en TBM Studio v.11, deberá utilizar la autenticación de cuenta de servicio.

    [Integración mediante autenticación de cuenta de servicio](#IntegratewithCostTransparency__Integrat2)

## Integrar utilizando autenticación Token ( R12+ )

1. En el menú Apptio Planning , seleccione **Configuración** y, a continuación **Cost Transparency Integration**.
2. En el panel Cost Transparency Integration , seleccione **Configurar**.
3. En General, introduzca lo siguiente:

   Método de autenticación
   :   Seleccione Autenticación por token ( R12+ ).

   Entorno
   :   Seleccione el Entorno en el menú desplegable.

   Instancia
   :   Introduzca la instancia Costing Standard .

   Dominio del proyecto
   :   Introduzca el dominio del proyecto Costing Standard .

   Importar desde
   :   Seleccione una de las siguientes opciones:
       - Desarrollo
       - Producción

         Si importa desde **Producción**, tendrá que esperar a que se completen los cálculos antes de que se muestren los datos.

   Funciones activadas
   :   Seleccione una de las siguientes opciones:

       - **Integración de planes** : permite exportar planes presupuestarios y previsiones a Costing Standard. En la lista **Formato de exportación**, seleccione una de las siguientes opciones:
         - **Publicar meses para todos los ejercicios fiscales como columnas en una única fila** : publicar cabeceras de columna mensuales utilizando el formato de fecha período número ejercicio fiscal. Por ejemplo, P1 FY2018.
         - **Publicar meses para todos los ejercicios fiscales como filas individuales** : incluye una columna de **Fecha** para el mes y el ejercicio fiscal, y una columna de **Importe** con la cantidad apropiada para ese período y ejercicio fiscal. Esta opción también utiliza el formato período número ejercicio.
       - **Reales** : permite importar los reales mensuales de Costing Standard
       - **Datos de referencia** : permite importar dimensiones predeterminadas y personalizadas, como Centros de coste y un plan de cuentas. Si decide integrar datos de referencia, asegúrese de que los nombres de los conjuntos de datos de referencia de la sección Planificación Costing Standard coinciden con lo que se cargó en Costing Standard.
       - **Configuración de exportación** : configure **la configuración de exportación** para definir el comportamiento predeterminado de exportación para todos los conjuntos de datos del plan. La configuración de exportación le permite controlar cómo se publican los datos del plan, incluyendo la selección del formato de exportación, la elección de la moneda predeterminada u original, la definición del formato de fecha y la precisión decimal, la aplicación de filtros de datos confidenciales y la configuración de si los meses se publican como filas o columnas (editado)
4. Seleccione Guardar.

## Integración mediante autenticación de cuenta de servicio

1. En el menú Apptio Planning , seleccione **Configuración** () y, a continuación, seleccione **Cost Transparency Integration**.
2. En el panel Cost Transparency Integration , seleccione **Configurar**.
3. En General, introduzca lo siguiente:

   Método de autenticación
   :   Seleccione Cuenta de servicio.

   Nombre de usuario
   :   Introduzca el nombre de usuario que desea utilizar para autenticarse en HTTP.

   Contraseña
   :   Introduzca la contraseña que desea utilizar para autenticarse en HTTP.

   Funciones activadas
   :   Seleccione una de las siguientes opciones:
       - **Integración de planes** : permite exportar planes presupuestarios y previsiones a Costing Standard. En la lista **Formato de exportación**, seleccione una de las siguientes opciones:
         - **Publicar meses para todos los ejercicios fiscales como columnas en una única fila** : publicar cabeceras de columna mensuales utilizando el formato de fecha período número ejercicio fiscal. Por ejemplo, P1 FY2018.
         - **Publicar meses para todos los ejercicios fiscales como filas individuales** : incluye una columna de **Fecha** para el mes y el ejercicio fiscal, y una columna de **Importe** con la cantidad apropiada para ese período y ejercicio fiscal. Esta opción también utiliza el formato período número ejercicio. Por ejemplo, P1 FY2018.
       - Reales **:** permite importar los reales mensuales de Costing Standard.
       - **Datos de referencia** : permite importar dimensiones predeterminadas y personalizadas, como Centros de coste y un plan de cuentas. Si decide integrar datos de referencia, asegúrese de que los nombres de los conjuntos de datos de referencia en la sección Planificación Costing Standard coinciden con lo que se cargó en Costing Standard
4. Seleccione Guardar.

## Importar datos reales de Costing Standard

1. Seleccionar ![img](../../../../../03-media/apptio-planning/resources/images/icons/icon-settings_20x20.png).
2. Seleccione **Cost Transparency Integration**.
3. Seleccione **Importar reales**.
4. Seleccione el Período inicial y el Período final de los datos que desea importar.
5. Seleccione **Importar**.

La importación funciona en segundo plano.

Para ver el progreso del proceso de importación, en la ventana Se ha puesto en cola la importación de reales, seleccione Estado.

- Si la opción **Importar desde Transparencia de Costes** no está disponible, o si la importación falla, es posible que su Cost Transparency Integration no esté configurado correctamente. Póngase en contacto con el servicio de asistencia designado o con el administrador.
- Si su organización utiliza varias divisas, deberá utilizar la misma tabla de tipos de cambio reales tanto para la aplicación Apptio Planning como para Costing Standard. Consulte [Compatibilidad con múltiples divisas](support-multiple-currencies.htm "(se abre en una pestaña o una ventana nueva)").

## Publicar planes para Costing Standard

Antes de publicar un conjunto de datos en Costing Standard desde su aplicación Apptio Planning , asegúrese de que el conjunto de datos existe en Costing Standard.

1. Seleccionar ![img](../../../../../03-media/apptio-planning/resources/images/icons/icon-settings_20x20.png).
2. Seleccione **Cost Transparency Integration**.
3. Seleccione **Publicar**.
4. En el menú desplegable, seleccione el plan que desea publicar.
5. Seleccione los tipos de partidas que desea publicar.
6. Seleccione **Publicar**.

El editor trabaja en segundo plano.

Para ver el progreso del proceso de publicación, en la ventana Su plan se ha puesto en cola para publicación, seleccione Estado.

- Si Project Financial Planning está habilitado, la **opción Publicar estados financieros a Costing Standard** La acción se moverá de la página **Todos los departamentos** > **Gastos** > **Resumen** a la página **Todas las secciones del plan** > **Libro mayor**. Esto publicará todas las partidas financieras directas, indirectas y de cargo en Costing Standard.
- Si la opción **Publicar en Costing Standard** no está disponible, o si la publicación falla, es posible que su Cost Transparency Integration no esté configurado correctamente. Póngase en contacto con el servicio de asistencia designado o con el administrador.
- Si su organización utiliza varias divisas, Apptio Planning las aplicaciones pueden publicar hasta 72 meses de datos en una sola acción de publicación (consulte [Compatibilidad con varias divisas](support-multiple-currencies.htm "(se abre en una pestaña o una ventana nueva)")).

## Importar datos de referencia de Costing Standard

Las tareas de esta sección sólo pueden ser realizadas por usuarios asignados a la función Admin. Ver permisos y roles de Frontdoor.

Los datos de referencia deben ser coherentes para que todas las funciones de información funcionen correctamente. Consulte [Gestionar datos de referencia](manage-reference-data.html "(se abre en una pestaña o una ventana nueva)"). Su aplicación Apptio Planning y los formatos de datos de Costing Standard no coinciden inicialmente con exactitud. Antes de continuar, ten en cuenta las siguientes diferencias de datos:

| Tabla | En qué fijarse |
| --- | --- |
| Cuentas | Los datos de referencia de la Cuenta en Costing Standard no incluyen:   - Grupo de cuentas - Subgrupo de cuentas - Fijo/Variable - Discrecional/No discrecional   Estas dimensiones aparecen en varios informes de Planificación. Debe incluir estas dimensiones además de la información estándar de la Cuenta. |
| Departamento | Los datos de referencia del departamento en Costing Standard no incluyen:   - Propietario (Owner) - Propietario del presupuesto   Estas dimensiones aparecen en varios informes de Planificación. Debe incluir estas dimensiones además de la información estándar del listado de Departamentos. |

Siga estos pasos para importar datos de referencia de Costing Standard. Al importar datos de referencia, se importa el conjunto de datos de referencia más reciente, independientemente de la configuración de fecha activa en Costing Standard.

1. Seleccionar ![img](../../../../../03-media/apptio-planning/resources/images/icons/icon-settings_20x20.png)
2. Seleccione **Cost Transparency Integration**.
3. Seleccione **Importar datos de referencia**.
4. En Categorías y Valores de importación, seleccione los conjuntos de datos que desea importar.
5. Seleccione **Importar**.

La importación funciona en segundo plano.

Para ver el progreso del proceso de importación, en la ventana Se ha puesto en cola la importación de datos de referencia, seleccione **Estado**.

**Tema principal:** [Conectarse a Apptio Costing](../../it-planning/planning/adm/adm_capabilities.html "Apptio La planificación se integra con Apptio el cálculo de costes mediante el sistema automatizado Data Management (ADM). ADM es un servicio de plataforma compartida diseñado para proporcionar una experiencia de intercambio de datos unificada, segura y escalable entre Apptio aplicaciones.")
