---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Apptio BI visión general"
breadcrumb: []
source_path: "it-planning/planning/ssr/it-planning-data-self-service-reporting.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Apptio BI visión general

Apptio BI permite a los usuarios crear y compartir sus propios informes personalizados utilizando datos de diversas aplicaciones, como Planning. Con los datos de Planning disponibles en Apptio BI, los usuarios pueden ahora crear un informe personalizado que resuma los datos laborales, de activos, de contratos y financieros del departamento Planning todos juntos.

Para saber más sobre Apptio BI, consulte [Apptio BI](../../../apptio_bi/home.html).

Nota:

Aunque admite la función multidivisa, Apptio BI sólo está disponible actualmente en inglés.

## Requisitos previos

Un administrador debe concederle permiso para acceder a Apptio BI. Si no tiene acceso, consulte [Apptio BI](../../../apptio_bi/home.html). Los siguientes Enhanced Access Administration Roles recibieron acceso de vista a Apptio BI :

- Administrador
- Propietario del centro de costes
- Propietario del proceso presupuestario

Los datos mostrados en Apptio BI se adhieren a los mismos permisos de vista configurados en Planning.

Si las fuentes de datos de Planning no aparecen en Apptio BI, trabaje con su gestor de atención al cliente para registrar Planning como fuente de datos en Apptio BI. Consulte aquí: Cómo registrar Planning como fuente de datos en Apptio BI.

## Datos disponibles

Los datos de gastos de todos los planes activos en Planning están disponibles para su uso en Apptio BI. Para ver una lista de los planes activos, seleccione Planes en el menú Planning (consulte [Cómo orientarse en Planificación](../navigate-apptio-planning.html) ). Para revisar los datos que estarán disponibles para un plan determinado, seleccione un departamento y, a continuación, Gastos en el menú Ver. Los datos de las pestañas Resumen, Mano de obra, Contratos y Activos estarán disponibles para la elaboración de informes. Los datos de la pestaña Resumen están disponibles seleccionando ITP Financials como fuente de datos.

Al crear una visualización en Apptio BI, se le pide que seleccione las dimensiones y métricas específicas de sus datos que desea incluir. Tenga en cuenta que las dimensiones de Apptio BI son distintas de las " [dimensiones de datos de referencia](../navigate-apptio-planning.html) " de Planning. Las dimensiones disponibles para los informes corresponden a las columnas de gastos en Planning. Las métricas corresponden a los valores indicados para cada periodo.

Para ver una lista de dimensiones para informes, complete los siguientes pasos:

1. En el menú Plan, seleccione un plan.

   Véase [Cómo orientarse en la planificación](../navigate-apptio-planning.html).
2. En el menú de navegación de la izquierda, seleccione Planning > Gastos.
3. En el menú de la sección Plan, seleccione un departamento.
4. Navegue a cualquiera de las siguientes pestañas: Resumen, Mano de obra, Contratos y Activos.
5. Haga clic en la flecha desplegable del nombre de una columna y, a continuación, en Mostrar/Ocultar columnas.
6. Las dimensiones disponibles corresponden a esta lista de columnas, independientemente de si la columna se muestra u oculta.

En Apptio BI, un informe es una colección de visualizaciones. Al crear un nuevo informe, éste estará vacío. Puede añadir visualizaciones al informe para mostrar los datos.

Se admiten columnas personalizadas para su uso en informes.

Acuérdate:

- Apptio BI informará con respecto a su entorno de producción Planning .
- Apptio BI requiere Planning 2.76 o posterior.
- Se admiten varias divisas.

Nota:

- Los datos laborales sensibles (como la remuneración base) no se exponen a Apptio BI.
- ITP DataSources en Apptio BI sólo muestra datos para el tipo de objeto de coste Departamento. Actualmente no se admiten datos de proyectos.
- Los datos relacionados con PFP, como las dimensiones de costes delegadas, no se exponen a Apptio BI hasta que se admita PFP.
- Datos de gastos reales de la Gestión de gastos.

## Descargar la lista de datos

Para consultar la lista de dimensiones y métricas disponibles en Planning en Apptio BI : [descargar como archivo.xslx](../../../resources/multimedia/itp%20-%20ssr%20integration/it%20planning%20data%20exposed%20to%20self%20service%20reporting_2020_12_08.xlsx).
