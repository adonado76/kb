---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Resumen del informe - Instancias reservadas"
breadcrumb:
  - "Costing Standard"
  - "Guía paso a paso del informe"
  - "Diseños de versiones anteriores"
  - "Informes en la nube"
source_path: "cost-transparency/reports-v104/reservedinstances.html"
images:
  - "resources/images/ct_images/reservedinstances_1.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Resumen del informe - Instancias reservadas

Nota: Se aplica a: Apptio Costing Standard en TBM Studio 12.3.3 y posteriores; Cloud Business Management en TBM Studio 12.6 y posteriores

El informe de instancias reservadas proporciona una explicación de su inventario actual de AWS y Azure instancias reservadas (RI), y puede ayudarle a tomar decisiones sobre las compras en curso de instancias reservadas. Azure las instancias reservadas están disponibles a partir de TBM Studio 12.6.

Este informe ofrece una visión de lo siguiente:

- El conjunto actual de instancias reservadas adquiridas por su organización
- Las instancias reservadas que han caducado recientemente o que van a caducar en breve

  Nota: Estas analíticas sólo se rellenarán si introduce sus compras de instancias reservadas a través de DataLink.
- Recomendaciones para adquirir instancias reservadas adicionales

  Nota: Estos análisis sólo se rellenarán si introduce sus datos de AWS Trusted Advisor. Para más información, consulte [Configurar recomendaciones para Public Cloud ahorro potencial](../user%20guide/configrecsforpubliccloud-7051.html "(se abre en una pestaña o una ventana nueva)").

## KPI

- **Coste facturado** : es el coste mensual y anual facturado real asociado a las compras de instancias reservadas de su organización. Estos datos proceden de las partidas de compra de instancias reservadas de su factura AWS.
- **Coste amortizado** - Se trata de los costes mensuales y anuales amortizados asociados a las compras de RI de su organización. Este coste se calcula en Apptio y distribuye los costes iniciales de la IR de manera uniforme a lo largo de la vida de la IR y añade los costes recurrentes mensuales. Estos datos proceden de las compras de RI que están separadas de su factura AWS.
- **Instancias que caducan pronto** - El número de instancias que caducarán en los próximos 30 días o que han caducado en los últimos 30 días. Estos datos proceden de los mismos datos de compra de RI utilizados para calcular el coste amortizado.
- **RI adicionales recomendadas para 1 año** - Las RI adicionales cuya compra se recomienda basándose en AWS Trusted Advisor y Azure Advisor.
- **ahorro total en 1 año** - El ahorro potencial asociado a las compras adicionales de RI recomendadas. Estos datos proceden de AWS Trusted Advisor.

## Informes

- Instancias reservadas **activas** - Un inventario y análisis de costes de las instancias reservadas que su organización ha adquirido.
  - **Basado en efectivo** - Esta pestaña proporciona una visión de sus costes de compra de RI facturados reales y se obtiene de la factura AWS.
    - **Recuento de instancias** : número de instancias asociadas a cada compra de instancia reservada.
    - **Coste de la factura en nube** - El coste facturado para el mes en curso.
    - **Cloud Invoice Cost YTD** - El coste facturado en lo que va de año.
  - **Base amortizada** - Esta pestaña proporciona una vista de los costes amortizados asociados a las IR que su organización ha adquirido. Los datos de esta pestaña proceden de las compras de RI, que se obtienen a través de las API de AWS, independientes de su facturación.
    - **Recuento de instancias** - Número de instancias asociadas a cada compra de RI.
    - **Coste inicial** - El coste inicial de la compra de RI.
    - **Coste mensual recurr** ente - El coste mensual recurrente de la compra de RI. Esto sólo se asociará a las compras de RI sin pago inicial o con pago inicial parcial, en las que se factura a su organización cada mes durante el plazo de vigencia de la RI.
    - **Coste mensual amortizado** - Se trata de un valor calculado en Apptio que se basa en la suma del coste inicial amortizado y el coste mensual recurrente.
- **Reservas que caducan** - Esta pestaña permite ver las IR que han caducado recientemente o que caducarán en breve.
- **Recomendaciones de compra de RI** - Esta pestaña se controla desde AWS Trusted Advisor RI Optimization check y Azure Advisor. Aflora las compras adicionales de RI que su organización puede realizar en función de su uso real a la carta de EC2. Para obtener más información de AWS, consulte la documentación de AWS Trusted Advisor: [https://aws.amazon.com/premiumsupport/ta-faqs/](https://community.apptio.com/external-link.jspa?url=https%3A%2F%2Faws.amazon.com%2Fpremiumsupport%2Fta-faqs%2F "(se abre en una pestaña o una ventana nueva)")
  - **RI adicionales recomendadas** - El número de RI adicionales que debería adquirir para lograr el ahorro de costes.
  - **Coste** inicial - Coste inicial requerido para las compras adicionales de RI recomendadas.
  - **Ahorro mensual estimado** - Importe aproximado del ahorro que se conseguirá con las compras adicionales de RI.
  - **Ahorro total a lo largo del plazo** - El ahorro total que se conseguirá a lo largo del plazo (1 o 3 años) de las compras adicionales de RI.
- **Consumo RI** - Esta pestaña ofrece una vista del consumo de sus instancias reservadas en función de la cantidad de uso y compara el consumo entre las instancias reservadas y los costes bajo demanda (disponible en v12.5+ ).
  - **Cantidad de uso** : el total de horas de instancia utilizadas durante el mes seleccionado
  - **Costes fijos** de RI: el total de costes de RI amortizados (recurrentes + amortizados por adelantado) asociados a la partida para el mes seleccionado
  - **Coste de utilización** : los costes totales a la carta asociados a la partida para el mes seleccionado
  - **Costes no relacionados con el proveedor** : los costes totales en los que se incurre como resultado del uso de la nube, pero que no están asociados a un proveedor de nube (por ejemplo, costes de software de terceros, costes laborales, etc.)
  - **Infraestructura de nube compartida** : los costes asociados a los servicios del proveedor de la nube que se comparten. Estos servicios compartidos podrían incluir Enterprise Support, VPC o cualquier otra herramienta o servicio básico utilizado para ofrecer aplicaciones o servicios en AWS.
- **AWS Utilización** de RI - Esta pestaña proporciona información sobre el uso de RI mes a mes, las tendencias de uso y la cantidad de dinero ahorrada en relación con las horas de RI. Cuando el uso a la carta supera el 100%, se muestra el coste del gasto excesivo.(Disponible en 12.6 y posteriores, con la plantilla v106 )
  - **Total de unidades reservadas** : número de horas reservadas para el mes seleccionado como parte de la compra de RI
  - **Cantidad utilizada** - Número de horas reservadas utilizadas por los recursos durante el mes seleccionado
  - **Porcentaje de utilización de la reserva** - Porcentaje de horas de RI adquiridas que se utilizan durante el mes seleccionado. Se calcula dividiendo la Cantidad Utilizada por el Total de Unidades Reservadas.
  - **Coste mensual efectivo** - Los costes de RI (amortizados por adelantado + recurrentes mensuales) para el mes seleccionado
  - **Coste hipotético a la carta** : el coste en que habría incurrido su organización en el mes seleccionado si no se hubieran adquirido RI. Se calcula multiplicando la Cantidad Utilizada por la tarifa Bajo Demanda para los tipos de instancias asociados a la partida de la tabla.
  - **Ahorro de costes / Gasto excesivo** : se trata del valor que se ha ahorrado al comprar RI o de cuánto ha gastado de más su organización al comprar RI y no utilizar plenamente esas compras de RI. Se calcula restando el coste hipotético a la carta del coste efectivo mensual.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/reservedinstances_1.png)
