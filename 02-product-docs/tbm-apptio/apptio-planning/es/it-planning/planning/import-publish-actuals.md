---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Importaciones reales"
breadcrumb: []
source_path: "it-planning/planning/import-publish-actuals.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Importaciones reales

Para ayudar a gestionar los gastos, se compara el plan presupuestario o la previsión con los datos reales históricos. La fuente de los datos reales puede ser su sistema de gestión financiera, TBM Studio, o Costing Standard.

## Rellenar el archivo.csv de datos reales

Importe los datos reales mes a mes. Para importar cada mes:

1. En el menú de navegación, seleccione Gestión de gastos > Transacciones.

   Nota:

   La función Aplicar permisos de visualización puede activarse en el Perfil de la empresa. Véase [Editar el perfil de la empresa](edit-company-profile.html "El Perfil de Empresa permite a los usuarios Administradores y Propietarios de Procesos Presupuestarios configurar los parámetros de la aplicación para personalizar la visualización, activar o desactivar funciones y definir el comportamiento del flujo de trabajo en Apptio Planning."). Si la función está activada, la página Gestión de gastos sólo es visible para
   - Propietarios del proceso presupuestario
   - Admins
   - Propietarios de presupuesto (que sólo pueden ver las transacciones de sus objetos de coste permitidos)
2. Seleccione Acciones > Exportar plantilla para descargar una plantilla que puede rellenar con sus datos reales. Su aplicación Apptio Planning descarga la plantilla de elementos de transacción en formato.csv.
3. Abra el archivo.csv descargado.
   - No cambie el nombre de los encabezados de columna en esta plantilla. La aplicación Apptio Planning requiere esta estructura de datos.
   - Los encabezados de columna de la plantilla deben estar en sus archivos para poder importarlos. Las cabeceras de las columnas pueden reordenarse.
   - Opcionalmente, añada encabezados de columna de dimensión personalizados a la plantilla (consulte [Añadir y gestionar atributos personalizados de dimensiones](manage_schema.html "Los esquemas definen la estructura de los datos en Apptio Planning. Especifican las tablas, campos y relaciones que determinan cómo se almacena, vincula y muestra la información en las pestañas de Gastos, como Trabajo, Contratos, Activos y Finanzas.")).
4. Pegue los datos reales del mes en la plantilla, asegurándose de que coincide con la estructura exacta mostrada en la plantilla. Añada información sobre el Centro de Coste y el Objeto de Coste. Los objetos de coste sin centros de coste no recibirán datos reales.
5. Guarde la plantilla en formato.csv en su unidad local.

## Importar el archivo.csv actual

1. En el menú de navegación, seleccione Gestión de gastos > Transacciones.
2. Seleccione un año y un mes para recibir los datos reales.
3. Seleccione Acciones y, a continuación, seleccione una de las siguientes opciones:
   - Importar datos reales - Importe un archivo.csv que contenga sus datos reales.
   - Importar de Costing Standard - Importe los datos reales de Costing Standard (véase [Integración con Transparencia de costes](integrate-ct.html "Si su organización utiliza tanto Apptio Costing Standard como una aplicación de planificación Apptio, puede integrarlas para compartir datos.") ).
4. Navegue hasta el archivo.csv que desee y haga clic en Importar.

## Abrir y ver los datos reales

1. En el menú de navegación, seleccione Gestión de gastos y, a continuación, seleccione un mes para verlo
2. Seleccione el mes de apertura.

Cuando se importan los importes reales, los importes reales y los importes plan aparecen en dos partidas separadas en la página Resumen o Libro mayor. Véase [Analizar un plan o una previsión](analyze-plan-forecast.html). Tenga en cuenta que:

- Los responsables del presupuesto pueden editar los atributos de las partidas previstas sin dejar de alinear los datos reales con el plan. Puede agrupar partidas individuales para ver los valores reales y plan en una sola partida individual y guardar estas configuraciones en una vista utilizando la función Diseños personalizados (véase [Personalizar, guardar y compartir diseños de tabla](customize-save-share.html)).
- Puede agregar atributos personalizados a la tabla que pueden ayudar a capturar información complementaria para mejorar el análisis y los informes (consulte [Agregar y administrar atributos personalizados de dimensiones)](manage_schema.html "Los esquemas definen la estructura de los datos en Apptio Planning. Especifican las tablas, campos y relaciones que determinan cómo se almacena, vincula y muestra la información en las pestañas de Gastos, como Trabajo, Contratos, Activos y Finanzas.").
- Al introducir datos en una tabla, puede introducir un valor trimestral o anual y esa cantidad se distribuirá proporcionalmente entre los meses.
- Si su organización gestiona tanto Planning como Apptio Costing Standard, puede integrar ambas para compartir datos (véase [Integración con Transparencia de costes](integrate-ct.html "Si su organización utiliza tanto Apptio Costing Standard como una aplicación de planificación Apptio, puede integrarlas para compartir datos.")).
