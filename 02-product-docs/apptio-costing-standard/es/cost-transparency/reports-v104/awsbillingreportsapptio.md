---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Visión general de los informes de facturación de AWS"
breadcrumb: []
source_path: "cost-transparency/reports-v104/awsbillingreportsapptio.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Visión general de los informes de facturación de AWS

Se aplica a: Costing Standard en TBM Studio 12.3.3 y posteriores

AWS ofrece varias fuentes de datos de facturación, cada una con sus propias características y usos. Para obtener más información, consulte [Comprender su uso con los informes de facturación - AWS Facturación y gestión de costes.](http://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/billing-reports.html "(se abre en una pestaña o una ventana nueva)")

Aunque Apptio admite datos de una gran variedad de fuentes, ofrecemos integraciones creadas específicamente en torno a un subconjunto de informes de facturación de AWS. Actualmente, Apptio ha creado integraciones con los siguientes informes de facturación:

- **Informe de imputación de costes** - Esta factura mensual de AWS incluye todos los datos de facturación (producto AWS, cantidad utilizada, coste, etc.) así como las etiquetas seleccionadas para ser incluidas en las facturas. Apptio aprovecha el Informe de Asignación de Costes para elaborar informes mensuales sobre el coste total de propiedad de la nube pública.
- **Informe detallado de facturación con recursos y** etiquetas: esta factura por horas de AWS es similar al informe de asignación de costes e incluye tanto detalles de facturación como etiquetas. Apptio aprovecha el informe de facturación detallado con recursos y etiquetas para impulsar los informes de costes diarios en Cloud Cost Management, que puede utilizar para ver los costes del mes hasta el día actual, así como la tendencia diaria y horaria de los costes de AWS.

El Informe detallado de facturación con recursos y etiquetas puede llegar a ser excesivamente grande ( 100M+ filas por mes) porque combina el detalle por horas con el detalle inherente a la facturación de AWS. A medida que aumentan los gastos de su organización en AWS, el tamaño de esta factura puede llegar a ser demasiado grande para introducirla en Apptio como archivo.csv nativo.

A partir de la versión Apptio 's 12.3.3 y Datalink (Classic), verá una nueva opción de transformación automática del conector AWS que le permite ingerir el Informe de Facturación Detallado con la factura de Recursos y Etiquetas en un nuevo formato sobre el que se construye el informe de Costes Diarios. Este nuevo formato, aunque sirve de base para los informes diarios de Cloud Cost Management, no está disponible actualmente para las transformaciones o el modelado en TBM Studio. El informe de asignación de costes sigue siendo la fuente de facturación mensual.

## ¿Qué pasa con el Informe de Costes y Utilización (CUR) de AWS?

AWS dispone de un informe de facturación más reciente que es la norma de referencia para las facturas de AWS. Apptio trabaja actualmente en la integración con el CUR y tiene previsto ofrecer un conector basado en el CUR en una próxima versión.
