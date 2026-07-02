---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Carga cruzada de la actividad laboral"
breadcrumb: []
source_path: "it-planning/planning/iip/configure-cross-charge.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Carga cruzada de la actividad laboral

Importante: *Disponible con la* *suscripción a* ***Apptio Planning Standard***

Cuando el proyecto utiliza recursos de mano de obra del Centro de Coste de Recursos, en el lado del Centro de Coste del Proyecto de la contabilidad el gasto de la actividad de mano de obra es un cargo o una cantidad de débito. Para evitar la doble contabilización del gasto, el propietario del Centro de coste de recursos debe recibir el cargo cruzado o el abono por la misma actividad.

Puede configurar el soporte de cargos cruzados en Integrated Investment Planning configurando los datos de referencia de la Cuenta de Actividad Laboral.

Para obtener más información, consulte [Gestionar los datos de la clase de actividad laboral](manage-labor-activity-type-data-ref.html)

Cuando la Clase de Actividad se establece en la línea de Actividad Laboral, los estados financieros se generan para asignar el cargo (débito) en la Cuenta de Cargo y el cargo cruzado (crédito) en la Cuenta del Centro de Costo de Recursos.

Si está asignando recursos del proveedor, en cuyo caso el gasto de la actividad laboral se contabiliza para el proyecto que utiliza esos recursos, pero no hay necesidad de realizar un cargo cruzado de ese gasto, puede implementar este caso de uso configurando el tipo de actividad de forma que tenga cuenta de cargo pero no cuenta de cargo cruzado.

Puede ver los importes de cargos y cargos cruzados generados en los respectivos centros de costes y cuentas en la vista Gastos > Resumen.
