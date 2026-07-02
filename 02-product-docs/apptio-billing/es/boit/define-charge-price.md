---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Definir la relación Precio x Cantidad"
breadcrumb: []
source_path: "boit/define-charge-price.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Definir la relación Precio x Cantidad

En el modelo de Cargo, primero debe definir los controladores al objeto de Alimentación de Consumo, y luego definir las asignaciones a la tabla modelada de Servicios Empresariales y a la tabla modelada de Asignación de Unidades Empresariales.

**Definir los controladores del objeto de alimentación de consumo**

Hay tres tipos básicos de controladores: los basados en costes, los basados en presupuestos y los basados en precios.

**Tarifas basadas en los costes**

Las tarifas basadas en costes repercuten el coste al usuario empresarial. Los costes por servicio se determinan en la aplicación Transparencia de Costes. Las tarifas basadas en los costes pueden tener información adicional proporcionada a través del feed de consumo.

1. Si aún no ha añadido datos al Feed de Consumo, vaya a [Añadir datos de consumo para cálculos de Precio x Cantidad](add-consumption-data.html "(se abre en una pestaña o una ventana nueva)"). Si no tiene intención de proporcionar cantidades, adjunte una lista de sus ID de servicio siguiendo los mismos pasos.
2. Siga los pasos descritos en [Definir las asignaciones del modelo de costes](define-cost-model1.html "(se abre en una pestaña o una ventana nueva)") para asignar costes al consumo.
3. En la tabla Biblioteca de servicios, establezca la **Metodología de tarificación** en **Coste** para todos los servicios que utilizarán Coste para determinar el cargo.
4. En el **Explorador de proyectos**, haga clic en el paso **Modelo** de la tabla Servicios empresariales.
5. Asegúrese de que está seleccionada la métrica **Carga**.
6. Validar que el controlador proporcionado muestra ahora los valores.

**Tasas basadas en el presupuesto**

Las tarifas basadas en el presupuesto pasan al usuario empresarial una tarifa presupuestada determinada por servicio. Los cargos basados en el presupuesto pueden tener información adicional proporcionada a través del feed de consumo.

1. Siga los pasos de [Añadir los datos de consumo](add-consumption-data.html "(se abre en una pestaña o una ventana nueva)").
2. En la tabla Biblioteca de servicios, establezca la **Metodología de fijación de precios** en **Presupuesto** para todos los servicios que utilizarán Coste para determinar el cargo.
3. En el **Explorador de proyectos**, haga clic en el paso **Modelo** de la tabla Servicios empresariales.
4. Asegúrese de que está seleccionada la métrica **Carga**.
5. Validar que el controlador proporcionado muestra ahora los valores.

**Tarifas basadas en el precio**

Las tarifas basadas en el precio multiplican un precio determinado por el servicio y las unidades del servicio que se han consumido. Los servicios basados en el precio deben tener feeds de consumo con las unidades proporcionadas a través del Feed de Consumo.

1. Siga los pasos de [Añadir los datos de consumo](add-consumption-data.html "(se abre en una pestaña o una ventana nueva)").
2. Siga los pasos de [Definir las asignaciones del modelo de unidades facturables](define-billable-model.html "(se abre en una pestaña o una ventana nueva)").
3. En la tabla Biblioteca de servicios, establezca la **Metodología de fijación de precios** en **Precio** para todos los servicios que utilizarán (Precio x Cantidad) para determinar el cargo.
4. En el **Explorador de proyectos**, haga clic en el paso **Modelo** de la tabla Alimentación de consumos.
5. Asegúrese de que está seleccionada la métrica **Carga**.
6. Validar que el controlador proporcionado muestra ahora los valores.

**Definir las asignaciones**

En el modelo de Cargo, debe definir la asignación desde el objeto del modelo de Alimentación de Consumo al objeto del modelo de Servicios Empresariales, y desde el objeto del modelo de Servicios Empresariales al objeto del modelo de Asignación de Unidades Empresariales. Utilice los ajustes que se muestran en las siguientes imágenes.

Asignación de consumo a los servicios a las empresas

Asignación de Servicios a Unidades de Negocio

Si no tiene ningún consumo o servicio atribuible en su totalidad a una unidad de negocio, utilice una asignación similar a:

En caso contrario, utilice esta asignación:
