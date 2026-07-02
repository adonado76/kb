---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Resumen del informe - Conciliar"
breadcrumb:
  - "Costing Standard"
  - "Guía paso a paso del informe"
  - "Diseños de versiones anteriores"
  - "Informes en la nube"
source_path: "cost-transparency/reports-v104/reconcile.html"
images:
  - "resources/images/ct_images/8094_1.png"
  - "resources/images/ct_images/8094_2.png"
  - "resources/images/ct_images/8094_3.png"
  - "resources/images/ct_images/8094_4.png"
  - "resources/images/ct_images/8094_5.png"
  - "resources/images/ct_images/8094_6.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Resumen del informe - Conciliar

Nota: Se aplica a: [Apptio Costing Standard](https://community.apptio.com/docs/DOC-8364.html "(se abre en una pestaña o una ventana nueva)") o [Apptio Cloud Cost Management](https://community.apptio.com/docs/DOC-8365.html "(se abre en una pestaña o una ventana nueva)") que se ejecuta en TBM Studio v12.3.3 o posterior.

## Visión general

Con Cloud Cost Management, Apptio ofrece la posibilidad de conciliar los costes y el consumo en Apptio con los comunicados por los proveedores de la nube en sus consolas de gestión de facturación. El informe Reconciliar de Gestión de costes en nube incluye informes flexibles que le permiten reconciliar a varios niveles dentro de su facturación y aislar subconjuntos específicos de costes (por ejemplo, para una sola cuenta o un subconjunto de cuentas) para reconciliar a un nivel más profundo.

## Conciliación de sus costes AWS

Con Amazon Web Services ( AWS ), puede conciliar su gasto mensual con los datos que AWS proporciona en su Panel de facturación. (Sólo tiene que seleccionar Detalles de factura y, a continuación, seleccionar el mes con el que desea conciliar)

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8094_1.png)

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8094_2.png)

Dentro de Apptio, el informe Reconciliar ofrece la posibilidad de ver tanto el coste como la cantidad de uso agrupados y filtrados por varios atributos de facturación, tales como, pero no limitados a, ID de cuenta (Pagador y/o Vinculado), Nombre de producto, Vendedor de registro y otros. Para empezar, puede agrupar sólo por ID de cuenta de pagador para obtener una vista del gasto mensual total de una cuenta de pagador principal.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8094_3.png)

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8094_4.png)

Esta cifra total debe coincidir con la cifra total de su factura AWS correspondiente al mismo mes.

**AVISO**

Si no ha incorporado sus facturas de AWS Marketplace y tiene cargos de AWS Marketplace, tendrá que conciliar con el total de AWS Cargos por servicio en lugar del total de AWS. Para obtener más información sobre cómo ingerir sus facturas de AWS Marketplace, consulte [Ingesta de facturación de AWS Marketplace](../user-guide/ingestingawsmarketplacebilling-6655.html "Si está consumiendo servicios de AWS Marketplace, querrá ingestar y modelar esas facturas de AWS Marketplace igual que ingiere y modela las facturas de servicios normales de AWS. AWS crea un archivo de facturación separado de AWS Marketplace para aquellos informes de facturación que haya configurado que se creen en sus preferencias de facturación. Al igual que con las facturas normales de servicios de AWS, Apptio recomienda utilizar el informe de asignación de costes del mercado AWS que agrega a nivel mensual.").

Puede empezar a añadir más detalles o filtrar por atributos específicos para conciliar a un nivel más profundo en su factura. Por ejemplo, puede conciliar cuentas vinculadas específicas seleccionando la casilla LinkedAccount, o filtrando por una cuenta específica en el cortador LinkedAccount. A continuación, en la factura de AWS, puede seleccionar los Detalles de la factura por cuenta y comparar los dos sistemas.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8094_5.png)

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8094_6.png)

## Conciliación de sus costes Azure

Para conciliar sus costes de Azure, puede verlos en su portal Azure y conciliarlos con los costes de Apptio a través del informe Microsoft Azure EA Detailed Bill. En el informe Apptio, puede variar el nivel y el subconjunto de elementos que desea conciliar utilizando los selectores y cortadores de atributos.
