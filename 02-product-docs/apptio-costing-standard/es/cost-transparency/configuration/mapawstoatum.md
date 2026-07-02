---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Mapa AWS Marketplace to ATUM"
breadcrumb: []
source_path: "cost-transparency/configuration/mapawstoatum.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Mapa AWS Marketplace to ATUM

Si consumes servicios de AWS Marketplace, debes ingerir y modelar esas facturas igual que tus facturas de servicios de AWS. AWS crea un archivo de facturación de AWS Marketplace independiente para cada informe de facturación que configure que se cree en sus preferencias de facturación.

Al igual que con las facturas de servicios típicas de AWS, Apptio recomienda utilizar el informe de asignación de costes del mercado AWS que agrega a nivel mensual. Para más información sobre los servicios de AWS Marketplace, visite [https://aws.amazon.com/marketplace/](https://community.apptio.com/external-link.jspa?url=https%3A%2F%2Faws.amazon.com%2Fmarketplace%2F "(se abre en una pestaña o una ventana nueva)").

Se aplica a: Apptio Costing Standard o Apptio Cloud Cost Management ejecutándose en TBM Studio v12.3.3 o posterior.

## Tarea 1: Configure un nuevo conector DataLink para automatizar la ingesta de su factura de Marketplace

### Procedimiento

1. Cree un nuevo conector Datalink (Classic) AWS, o copie un conector AWS existente (Más información).
2. Configure la autenticación.

   Nota: Al utilizar la delegación, si copia un conector existente, esta sección ya estará rellenada.
3. Haga clic en Informe de facturación.
4. En Tipo de informe, seleccione Avanzado.
5. En File Pattern, escriba el siguiente patrón:"<su número de cuenta AWS >-aws-cost-allocation-AWSMarketplace- {CYYY} - {MM}.csv>"
6. Configure el destino Apptio, las notificaciones y la programación en función de sus necesidades específicas.
