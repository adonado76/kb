---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Requisito de datos de referencia"
breadcrumb: []
source_path: "it-planning/planning/import-publish-currency.html"
images:
  - "resources/planning_images/itp_currency-converion-rate-table-example.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Requisito de datos de referencia

Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.

Apptio Planning admiten dos tablas de tarifas distintas:

- Tabla de tipos de conversión de divisas del plan - Utilícela para todas las conversiones de divisas en los planes y previsiones presupuestarios
- Tabla de tipos de cambio de los datos reales - Se utiliza para convertir los datos reales registrados en varias monedas locales a una moneda común para obtener vistas resumidas de los datos reales

Los tipos de conversión de moneda Plan y Real forman parte de las dimensiones incorporadas que se gestionan en los datos de Referencia. Consulte [los datos de referencia de las tablas de tipos de cambio](manage-multi-currency.html "Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor."). Especifique el tipo de conversión entre la moneda común de su organización y otra moneda. Véase [Fijar la moneda común](set-common-currency.html "Se utiliza una única moneda común para todas las conversiones monetarias. La moneda común suele ser la moneda de registro de la organización. Todas las tasas de conversión de moneda se fijan contra esta moneda y, a menos que se especifique otra, es la moneda de visualización por defecto por Centro de Coste."). Opcionalmente, puede especificar un periodo de tiempo durante el cual se aplicará un tipo de conversión específico.

## Descargue y rellene la plantilla de la tabla de tipos de cambio

Para crear un dato de referencia:

1. Asegúrese de que la compatibilidad con varias monedas esté habilitada (consulte [Compatibilidad con varias monedas](support-multiple-currencies.html) ).
2. En el menú de navegación, seleccione Configuración > Datos de referencia. Dispone de dos tipos de moneda: Tipo de moneda real y Tipo de moneda plan.
   - Los datos de referencia Actuals Currency Rate definen los tipos de cambio utilizados para convertir varias monedas a una moneda común. Esto le permite ver vistas resumidas de los datos reales:

     ![imagen](../../resources/images/it%20planning_images/actuals-currency.png)
   - Los datos de referencia del tipo de moneda del plan definen los tipos de conversión de moneda utilizados para convertir varias monedas a una moneda común en los planes y previsiones presupuestarios:

     ![imagen](../../resources/images/it%20planning_images/plan-currency.png)

     Consulte [los datos de referencia de Gestionar tablas de tipos de conversión multidivisa](manage-multi-currency.html "Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.").

     Nota: Debe exportar una plantilla para Moneda real y Moneda plan. Si su aplicación Apptio
     Planning está integrada con Costing Standard, debe utilizar la misma tabla de tipos de cambio reales para ambas aplicaciones.
3. Abra el archivo de plantilla.csv. No cambie los títulos de las columnas ni la estructura de esta plantilla.
4. Introduzca los valores de su tasa de conversión. Las opciones por valor de moneda incluyen:
   - Una única tasa de conversión que abarca todos los periodos de tiempo.
   - Tipos de conversión variables según el valor de la divisa. Especifique un período de inicio Efectivo desde para un tipo de conversión específico. A continuación, especifique las fechas de inicio de otros periodos de tiempo para ese mismo valor de moneda.
5. Opcionalmente, incluya una fila para la moneda común con un tipo de conversión de 1. Si no lo hace, aparecerá una alerta, y esto se hará por usted cuando importe la tabla de tarifas.CONSEJO: Sus aplicaciones Apptio Planning trabajarán con los datos de la tabla de tarifas en cualquier orden de filas, pero los encabezados deben permanecer en la fila 1. Al editar el archivo.csv, puede ordenarlo por cualquier encabezado de columna (por ejemplo, ordenar por fecha o por código de moneda). El orden de clasificación que utilice se aplicará a la tabla de tipos de cambio una vez importada a su aplicación Apptio Planning .
6. Guarde la plantilla en formato.csv para su importación.

Por ejemplo, los valores de la tabla de tipos que fijan los tipos de cambio mensuales para la moneda de la empresa dólar estadounidense y el euro:

![imagen](../../../../../03-media/apptio-planning/resources/planning_images/itp_currency-converion-rate-table-example.png)

En esta tabla de ejemplo, todas las conversiones Dólar estadounidense/Euro anteriores al 1 de enero de 2016 (1) utilizan el tipo de conversión 0.88. A continuación, la tarifa se ajusta mensualmente como se indica (2). Dado que no se especifican tipos de conversión posteriores, todas las conversiones posteriores al 1 de marzo de 2016 utilizarán el tipo 0.91 (3).

Cuando publique las tarifas, estarán disponibles aquí: En la navegación de la izquierda, seleccione Planning > Gastos > Resumen, y las tarifas publicadas estarán disponibles en cada una de estas pestañas: Resumen, Mano de Obra, Contratos, Activos, Otros.. También podrá seleccionar las vistas en función de las divisas que se publiquen.

## Importación y publicación de tablas de tipos de cambio

Para cargar y publicar los datos de referencia de las tablas de tipos de cambio de divisas, consulte [Administrar datos de referencia de tablas de tipos de cambio de divisas múltiples](manage-multi-currency.html "Las siguientes tareas sólo pueden ser realizadas por usuarios asignados a los roles de Administrador o Propietario de Proceso Presupuestario. Para obtener más información sobre las funciones, consulte Permisos y funciones de Frontdoor.").

## Resolución de problemas

En esta sección, puede encontrar algunos errores frecuentes y soluciones a los mismos.

[Sus KPI o valores en un plan muestran el error #REF](ts_ref-error-kpi-plan.html)
