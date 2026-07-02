---
source_system: "apptio-costing-essentials"
practice: "tbm"
language: "es"
doc_type: "apptio-cost-management"
title: "Repercusiones"
breadcrumb:
  - "Costing Essentials"
  - "Entorno de trabajo"
source_path: "apptio-cost-management/workbench/fallout.html"
images:
  - "resources/images/studio_images/fall-labor.png"
  - "resources/images/studio_images/fall-oth_958x601.png"
  - "resources/images/studio_images/fall-sol.png"
  - "resources/images/studio_images/fall-vendor.png"
  - "resources/images/studio_images/fallout-1_1202x762.png"
  - "resources/images/studio_images/fallout-2_1017x447.png"
capability_ids: []
last_updated: "2026-02-27"
summary: ""
---
# Repercusiones

El Panel de Fallout destaca fácilmente los costes - tanto OpEx como CapEx - en su modelo Costing Essentials que se han asignado completamente o no se han asignado (fallout).

## KPI

Ofrece una visión general del coste total en cada nivel del modelo. Un modelo totalmente asignado mostrará el mismo coste total en cada KPI.

Ejemplo:

- Fuente de costes - Gasto total hasta la fecha = 100 dólares
- Soluciones - Gasto total hasta la fecha = 80 dólares
- Unidad de negocio - Gasto total hasta la fecha = 50 dólares

## Fuente de costes

Utilice este informe para ver la Distribución OpEx (Mano de obra, Proveedores, Otros) por periodo y asegurarse de que sus Transacciones GL coinciden con el objeto Fuente de Coste dentro de ACM.

![imagen](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/fallout-1_1202x762.png)

Según el diseño, hay una asignación que envía todo el coste restante a Otros - es decir, el coste que no se ha asignado a Proveedor o Mano de obra -. Por lo tanto, no hay consecuencias de la fuente de costes, y para garantizar que el coste que fluye a través de Otros es legítimo, mostramos el coste mal asignado en una tabla debajo del gráfico. "Mal asignado" significa que este coste enviado a Otros, debería haber sido enviado a Proveedor o Mano de obra, pero falló debido a que la Relación no coincidía.

Ejemplos:

- En un determinado GL Real, el Pool de Costes es Mano de Obra Interna para la Cuenta, pero no podemos encontrar ningún HC de Mano de Obra asociado al mismo Centro de Coste en Datos Laborales.
- En un determinado libro mayor real, se ha asignado un ID de proveedor, pero no podemos encontrar este ID de proveedor en la lista maestra de proveedores (que podría ser el caso si el proveedor se ha eliminado de la lista maestra de proveedores utilizada para el mes seleccionado)

![imagen](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/fallout-2_1017x447.png)

## Trabajo

Utilice este informe para ver los costes de mano de obra no asignados que se espera asignar a Soluciones. Para solucionar cualquier incidencia, el usuario debe utilizar las tablas de "Asignación de mano de obra" para asignar un recurso de mano de obra a ofertas de soluciones individuales.

![imagen](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/fall-labor.png)

## Proveedores

Utilice este informe para ver los costes de proveedor no asignados que se espera asignar a Soluciones. Para solucionar cualquier incidencia, el usuario debe utilizar las tablas de "Asignación de proveedores".

![imagen](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/fall-vendor.png)

Nota: cuando las columnas de búsqueda [En tipo de catálogo], [En categoría de catálogo], [En ID de oferta de catálogo] están resaltadas en rojo, significa que los datos asignados en el Workbench ya no se encuentran en el Catálogo de Servicios. Esto puede ocurrir cuando se actualiza el Catálogo de Servicios sin actualizar las asignaciones de Recursos para alinearlas con el nuevo Catálogo de Servicios.

## Soluciones

Utilice este informe para ver los costes de Solución no asignados que se espera asignar a Organizaciones (Consumidores). Para solucionar cualquier incidencia, el usuario debe utilizar las tablas "Asignación de soluciones" o "Asignaciones de organizaciones" según se indica en la columna "Acción de solución de incidencias".

![imagen](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/fall-sol.png)

## Otros

El coste fuera de Otros siempre se imputa, ya que funciona como imputación de costes de "Envío restante". La siguiente instantánea indica los detalles de este coste asignado.

![imagen](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/fall-oth_958x601.png)
