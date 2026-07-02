---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Azure Instancias reservadas - Ingesta y asignación de costes"
breadcrumb: []
source_path: "cost-transparency/configuration/azurereserved.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Azure Instancias reservadas - Ingesta y asignación de costes

Microsoft Azure lanzó las instancias reservadas (IR) a finales de 2017. Los costes asociados a estas IR pueden ser considerables y deberán tenerse en cuenta a la hora de considerar su gasto en Azure.

Se aplica a: Gestión de costes en la nube en TBM Studio 12.5 +.

## Visión general

En la actualidad, los cargos de RI no se reflejan en la factura de EA de Azure, sino que tienen que ingestarse por separado y luego asignarse a los recursos apropiados (VM), de modo que los costes efectivos de esas VM se calculen adecuadamente.

Esta guía proporciona los pasos necesarios para incorporar los cargos de RI de su organización y asignarlos con precisión a los recursos apropiados en su factura de EA de Azure.

Implicaciones en la adaptación:

- Gastos de acceso a la instancia reservada: los gastos de RI no se reflejan en la factura de EA de Azure y deberán introducirse en Apptio a través de un conector REST de Datalink (Classic).
- Amortización y asignación de los costes de las instancias reservadas: los costes de las IR deberán amortizarse a lo largo del periodo de vigencia de la IR y, a continuación, asignarse a los recursos de la factura que se beneficien de esas compras de IR.
