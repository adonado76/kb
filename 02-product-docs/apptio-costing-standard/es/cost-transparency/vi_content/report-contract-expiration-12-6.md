---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Caducidad del contrato"
breadcrumb:
  - "Costing Standard"
  - "Guía paso a paso del informe"
  - "Cobro a proveedores"
source_path: "cost-transparency/vi_content/report-contract-expiration-12-6.html"
images:
  - "resources/images/vi_images/vi/alertsicon.jpg"
  - "resources/images/vi_images/vi/contract-expiration-report-12-6_main.jpg"
  - "resources/images/vi_images/vi/export.jpg"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Caducidad del contrato

◆ Aplicable a: Vendor Insights en TBM Studio 12.8 y versiones posteriores ( v107 )

Utilice el informe de vencimiento de contratos para analizar de forma proactiva los contratos antes de su vencimiento y renovación. Este informe está diseñado para:

- Gerentes de proveedores
- Propietarios de servicios
- Propietarios de aplicaciones
- Gerentes de finanzas de TI
- Director de informática y altos cargos de TI

**Mostrar el informe de vencimiento de contratos**

En el menú Aplicaciones, seleccione Vendor Insights .

1. Vaya a Colecciones de informes > Contratos.
2. En la barra situada en la parte superior de la página, seleccione Vencimiento del contrato.
3. Opcionalmente, filtre el informe utilizando las opciones situadas en la parte superior del mismo.
4. Para exportar o enviar por correo electrónico tus datos, selecciona Exportar ( ![imagen](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/export.jpg) ) en la parte superior derecha de la página y selecciona un formato de exportación.
5. Para crear una alerta que le notifique si un contrato está a punto de caducar, seleccione Alerta ( ![imagen](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/alertsicon.jpg) ) en la parte superior derecha de la página. Para obtener más información, consulte [Crear alertas para contratos de proveedores que están a punto de caducar](alerts.html).
6. Seleccione cualquier elemento de la columna Título del contrato de la tabla del componente del informe Detalles de vencimiento del contrato para abrir el informe Detalles del contrato correspondiente a ese contrato. Para obtener más información, consulte [el informe Detalles del contrato](report-contract-detail.html).

El informe contiene los siguientes elementos:

![imagen](../../../../../03-media/apptio-costing-standard/resources/images/vi_images/vi/contract-expiration-report-12-6_main.jpg)

**(1) Recopilación de informes**

Esta recopilación de informes proporciona los detalles que necesita para analizar el gasto de su cartera de proveedores por tipo de proveedor y periodo de tiempo:

- [Resumen del contrato](report-contract-summary.html)
- Informe de vencimiento de contratos (descrito en este artículo)
- [Informe sobre contratos y aplicaciones](report-contract-applications.html)
- [Informe de notificación de vencimiento del contrato](report-contract-expiration-notification.html)

**(2) Cortadoras**

Los siguientes filtros globales están disponibles en esta colección de informes:

- **Gerente** de proveedores: filtre por una persona específica para ver el impacto de los proveedores gestionados por esa persona.
- **Nombre normalizado del proveedor** : filtra por un proveedor específico.

**(3) Indicadores clave de rendimiento (KPI)**

Los KPI proporcionan una visión general del gasto en proveedores y la expiración de los contratos:

- **Importe que vence en 30 días** : este KPI muestra el gasto total del periodo actual y el número de proveedores que han realizado gastos en el periodo actual. El gasto es la suma de todas las cuentas por pagar en el período actual.
- **Importe con vencimiento entre 31 y 60 días** : este KPI muestra el gasto total en proveedores en lo que va de año y la diferencia en el gasto en lo que va de año entre el año anterior y el actual.
- **Importe con vencimiento entre 61 y 90 días** : este KPI muestra el número de contratos que vencen en menos de 90 días y en menos de 180 días.
- **Importe con vencimiento entre 91 y 180 días** : este KPI muestra el gasto mínimo comprometido para los contratos que vencen en menos de 90 días y en menos de 180 días.

**(4) Tendencia de vencimiento de los contratos**

Utilice esta sección para saber cuántos contratos vencen en los próximos meses o trimestres (gráfico de líneas) y el importe de los contratos afectados (gráfico de barras). Esta sección le ayuda a visualizar el impacto de los próximos vencimientos de contratos y el esfuerzo que podría ser necesario para planificar las renovaciones de los mismos.

- Haga clic en la pestaña **1 año (mensual)** para ver el importe del contrato y el número de contratos con proveedores que expirarán en los próximos 12 meses, en incrementos mensuales. Para ver el importe total mensual de los contratos que vencen, pase el cursor por encima del gráfico de barras.
- Haga clic en la pestaña **3 años (trimestral)** para ver el importe del contrato y el número de contratos con proveedores que expirarán en los próximos tres años, en incrementos trimestrales.

**(5) Detalles sobre la expiración del contrato**

Utilice esta sección para ver los detalles de los contratos que vencen por período. Puede ver el contrato con mayor gasto durante un período de tiempo seleccionado ordenando la columna **Importe del contrato**.

Utilice las pestañas para ver los diferentes periodos. Configurar un filtro te permite reducir los resultados según sea necesario. Para obtener más detalles sobre un contrato específico, haga clic en la columna **Título del contrato** para abrir el [informe Detalles del contrato](report-contract-detail.html).

El valor de **Días de notificación** aparecerá resaltado en rojo cuando un contrato haya superado la fecha de vencimiento, para que puedas notificar al proveedor que actualice el contrato.

A partir de la versión 12.7, se ha añadido una columna para **Suprimir alerta** a la tabla Detalles. **Sí** significa que las alertas se suprimen para el contrato.

Preguntas respondidas

- ¿Qué contratos vencen y cuándo?
- ¿Qué contratos están pendientes de renovación y cuándo?
- ¿Cuáles son mis contratos críticos y los servicios que prestan?
