---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Añadir un paso de fórmula a 12.6 cloud tables"
breadcrumb: []
source_path: "cost-transparency/configuration/addformulastep.html"
images:
  - "resources/images/ct_images/10838_1.png"
  - "resources/images/ct_images/10838_2.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Añadir un paso de fórmula a 12.6 cloud tables

Actualmente, Apptio no admite la adición de pasos de fórmula a las tablas de nubes AWS y Azure. Sin embargo, si surge la necesidad (por ejemplo, si necesita modificar Costes), utilice la siguiente solución.

Se aplica a: Cloud en Costing Standard y Cloud Business Management (CBM) en TBM Studio 12.6 o posterior

Para añadir un paso de fórmula a su informe mensual AWS, haga lo siguiente:

## Procedimiento

1. Desmonte el **AWS Cost and Usage Raw** de los **AWS Cost** and **Usage Master Data**.
2. Cree una transformación a partir del último paso de la Tabla de canalización y nómbrela **AWS Transformación de coste y uso**. Colóquelo en la **categoría de proveedor de servicios en nube**.
3. Adjunte la **transformación de uso y costo AWS** a los **datos maestros de uso y costo AWS**.
4. Asigne los siguientes campos:

   - Coste = Coste sin mezclar del proveedor
   - Coste del proveedor = Coste no combinado del proveedor
   - RowID = ID de fila

## 

Para añadir un paso de fórmula a su informe mensual Azure, haga lo siguiente:

### Procedimiento

1. Desasocie el **Azure EA Bill Raw** de los **Azure EA Bill Master Data**.
2. Cree una transformación a partir del último paso del pipeline Tabla, y nómbrela Azure EA Bill Transform. Colóquelo en la categoría de proveedor de servicios en nube.
3. Añada Azure EA Bill Transform a Azure EA Bill Master Data. Todos los campos deberían asignarse automáticamente.

### Ejemplo

![Azure EA Bill Raw](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/10838_1.png)![Azure EA Bill Raw 2](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/10838_2.png)

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
