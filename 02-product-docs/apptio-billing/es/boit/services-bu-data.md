---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Añadir datos presupuestarios de servicios y unidades de negocio"
breadcrumb: []
source_path: "boit/services-bu-data.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Añadir datos presupuestarios de servicios y unidades de negocio

Añada datos presupuestarios de servicios y unidades de negocio sólo si ha instalado el componente**Billing Standard - Desviación del plan**. Los datos se utilizarán para comparar el gasto previsto con el gasto real. Si no ha instalado el componente**Billing Standard - Desviación del plan**, no realice este paso. Si ya tiene un modelo de presupuesto configurado en su proyecto de Transparencia de Costes, utilice ese modelo de Presupuesto y asigne desde las Torres de Recursos TI a la Alimentación de Consumo.

**Datos necesarios**

Los datos deben incluir las columnas que se describen a continuación.

- ID de **servicio** : debe coincidir con los ID de servicio de la tabla de la biblioteca de servicios.
- **Presupuesto total del servicio por mes** - Si está cargando un año entero de datos, incluya columnas separadas para cada mes del año. Después de cargar los datos, añada un paso de partición de fecha al proceso de transformación.
- ID de unidad de **negocio (opcional)** - Debe coincidir con los ID de unidad de negocio de la tabla Servicios de negocio.

Cuando cargue la tabla, nómbrela `Service and Business Unit Budget Data` y colóquela en la categoría **General**.

**Utilizar los datos en modelos**

Para utilizar los datos presupuestarios de servicios y unidades de negocio en los modelos, realice las siguientes tareas.

1. Añada un paso del modelo a la tabla de Datos Presupuestarios de Servicios y Unidades de Negocio.
2. En los modelos Presupuesto y Presupuesto empresarial, añada un controlador de unidad basado en la columna de presupuesto de la tabla.   
    Si desea comparar el coste y el cargo con presupuestos separados, añada dos controladores: uno para Presupuesto de empresa y otro para Presupuesto.
3. Añade una asignación al objeto modelo Business Services.
